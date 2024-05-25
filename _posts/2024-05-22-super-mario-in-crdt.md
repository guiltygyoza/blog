---
layout: post
title:  "Super Mario in CRDT"
date:   2024-05-22 00:00:00 -0500
categories: idea
published: true
---

Credits to Matthew Demoy and Jihoon Song for making Penguin World a reality.

### Why?
Why making Super Mario in CRDT?

What does it mean?

Implementing a multiplayer game in [CRDT](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type){:target="_blank"} would enable pure peer-to-peer gameplay. No super nodes endowed with asymmetric power to determine the evolution of the game authoritatively. Infrastructure-less*. CRDTs mathematically guarantee that all peer replicas can write at the same time (multi-writer), never block one another (lock-free asynchrony), and that they will eventually converge to the same state with probability 1. It also means the game is automatically load-balanced across all players.

Topology Protocol intends to be a protocol about peer-to-peer [BFT-CRDT](https://martin.kleppmann.com/papers/bft-crdt-papoc22.pdf){:target="_blank"} objects, or Conflict-free Replicated Objects (CROs). One use case of a CRO is to implement multiplayer peer-to-peer games. Long before we began conceptualizing the protocol, we wanted to see from our eyes if a game like Super Mario can be implemented in CRDT. So we took [Yjs](https://github.com/yjs/y-webrtc){:target="_blank"} and created Penguin World, a multiplayer platformer lobby prototype.

**Almost* infrastructure-less. For example, if using [WebRTC](https://webrtc.org/){:target="_blank"}, there is the need for WebRTC signaling to establish connection. Relay servers are needed if [NAT](https://en.wikipedia.org/wiki/Network_address_translation){:target="_blank"} is a problem.

### Yjs
Yjs implements common data types in CRDTs for making collaborative software. Yjs calls these data types "shared types". Projects like Evernote and JupyterLab use it.

Here's how it works. In Yjs land, when you build a collaborative application, you will need some state data that are shared: multiple users can access and mutate them concurrently. All these shared data should be typed with Yjs's shared types, and are typically defined in a collection called Yjs Document or `YDoc`.

Here's an example of a `YDoc` that holds a `YArray` and a `YMap`:
```
// grab an empty YDoc
const ydoc = new Y.Doc()

// under YDoc, define a YArray instance for chat history
const yarray = ydoc.getArray('chatHistory')

// under YDoc, define a YMap instance for user accounts
const yarray = ydoc.getMap('userAccounts')
```

In vivo, every user running this application would have a copy of the app's `YDoc`. Users can mutate their local copies of the `YDoc` asynchronously. Yjs guarantees all these copies are in sync. If two `YDoc` copies are the same, the two users would see the same thing on their screens.

Although Yjs was made for collaborative software, we intuited that it could be repurposed for multiplayer games. After all, the kind of conflict in users typing into the same document location is not too different from the kind of conflict in users moving their player characters into the same spot in a game world, right? To figure out, we made Penguin World.

### Penguin World
Penguin World is a multiplayer platformer lobby. Every user controls a penguin that can move left and right, jump, and shoot snowballs. When penguins collide, they bounce off each other. When snowballs hit penguins, snowballs stop and disappear.

Text chat and voice chat are also implemented. When sending a message in the text chat, the same message would appear above the sender penguin's head and disappear after a while.

<img src="/assets/2024-05-22/penguin-snowball-party-short-speed.gif" width="720">

### Penguin World under the hood
The [code](https://github.com/topology-gg/esotere-client){:target="_blank"} is open source.

Penguin World's core game states are represented in Yjs's shared types:
1. A `YMap` maps player ID to a player state struct, which includes: player name, penguin position, penguin's animation state, text above penguin's head, audio stream status, and a mailbox for players to pass messages to one another. These messages are used for collision resolution, to be explained below.
2. A `YArray` records text chat messages.

[y-webrtc](https://github.com/yjs/y-webrtc){:target="_blank"} is used as the transport mechanism to connect all peers. Voice chat is peer-to-peer as well and built with [SimplePeer](https://github.com/feross/simple-peer){:target="_blank"}, which also uses WebRTC. Finally, [PhaserJS](https://github.com/phaserjs/phaser){:target="_blank"} handles rendering, input capture, ticking, and single-player physics.

Penguin-penguin collision resolution is achieved by a pretty wacky approach: message-passing between players. Recall that every player state struct contains a mailbox. Collision resolution works as follows, assuming Alice and Bob are two players and assuming Alice just saw Bob's penguin overlapping with hers in her local view:
1. Alice calculates the displacement vector between the geometric centers of the two penguins.
2. Using that vector, along with a number that represents the idea of restitution coefficient, Alice calculates two velocity vectors in opposite directions, one for her penguin and the other one for Bob's. These velocity vectors are meant to be applied to resolve the collision.
3. Alice applies her velocity vector immediately, while pushing a collision-resolution message containing Bob's velocity vector into Bob's mailbox. Literally Alice is shouting at Bob "hey you should kick yourself by this much so that we stop colliding!"
4. Bob checks his mailbox, pops the message, and applies the velocity change.

### Scalability
With y-webrtc, every client is connected to every other client by default. This approach is not suitable for a large amount of concurrent users. Scalability could be improved in different ways such as adopting a mesh topology for peer-to-peer connection and compressing outbound messages.

### Byzantine faults
The code, running purely client-side, can be modified to update CRDTs in ways that deviate from the expected behavior. We can loosely call these deviations Byzantine faults. Examples include:
1. **Teleportation**. A dishonest client can update their own player state arbitrarily, bypassing PhaserJS physics.
2. **Telekinesis**. A dishonest client can push arbitrarily collision-resolution messages to other player states. Eve can shout to Alice "hey you should kick yourself by this mcuh so that we stop colliding!" without Eve actually seeing the overlapping of their penguins. The velocity vector can be arbitrarily chosen too.
3. **Time-related hacks**. Anything involving local machine time is vulnerable to Byzantine behavior. For example, a client can change its tick rate in PhaserJS and cause its player to move faster or slower than other players.

Both the teleportation and telekinesis problem can be addressed by having the CRDTs "absorb" the physical laws of the game world. Time-related hacks seem tricker.

Interestingly, as Penguin World is running peer-to-peer between players directly, being intolerant to Byzantine faults means *any* player can screw up or violate the norm one-sidedly. And since every CRDT update can be traced to its producer, Byzantine behavior is detectable (Yjs does not implement asymmetric cryptography but it is doable). This property makes Penguin World a trustful and collaborative space: everyone is trusted and expected to uphold the rules and values; anyone who doesn't will be spotted.

As to how to recover from dishonest updates once they are detected is another story. For example, if the detection does not happen in time, more updates could have already happened after and causally depended* on the dishonest updates such that recovery involves rolling them back.

*Yjs shared types do not provide causal consistency.

### Towards Topology Protocol
We are fascinated by the affordnace of lock-free asynchronous interaction provided by CRDT/[OT](https://en.wikipedia.org/wiki/Operational_transformation){:target="_blank"} techniques and we are actively creating a [protocol](https://github.com/topology-foundation/paper){:target="_blank"} about Conflict-free Replicated Objects or CROs. We believe that CROs complement smart contracts in the tradeoff space of consistency models, and that combining them would take the expressiveness of decentralized applications to a whole new level.
