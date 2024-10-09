---
layout: post
title:  "From Ledgers to Sandcastles - Part 2"
date:   2024-10-09 00:00:00 -0500
categories: idea
published: true
---

<img src="/assets/castle.png" width="700">

This essay is also published on [Topology's Blog](https://blog.topology.gg/the-origins-of-topology-from-ledgers-to-sandcastles-part-2/){:target="_blank"}. The castle drawing is produced by [Ranyah Al-gubani](https://x.com/ra_algubani){:target="_blank"}.

# CRDT: the magical sand
**CRDT** is the magical sand. Its full name is **C**onflict-free **R**eplicated **D**ata **T**ype. What a mouthful! Fear not, let’s break it down in simple words.

**D**ata **T**ype is the easy part. Think of it as sand types. Sand comes in vastly many types — river sand, sea sand, mountain sand, clay sand, quartz sand and so on. They differ in properties such as strength, permeability, and adhesiveness. They suit different purposes.

**R**eplicated means it exists in the form of copies (or replicas, as the fancy people call them). It may be a strange concept — a heap of sand that doesn’t exist in one place but many places all at once? That is precisely the point! If the sand exists in one place only, anyone who wishes to manipulate the sand needs to visit that place. It is entirely centralized, making that place the bottleneck of the entire party that wishes to collaborate. “No,” said the magical sand, “I exist in equal copies. If you wish to manipulate me, a copy of me will zip to you and sit in your computer. You can manipulate your copy however you want.” (For the curious: in computer science, a software object that is replicated is often called a [distributed object](https://en.wikipedia.org/wiki/Distributed_object){:target="_blank"})

Not so fast, you thought. If everyone is manipulating their own copy of the heap of sand, in effect they are manipulating different heaps of sand, which means they are not actually collaborating, no? The thing is these copies actually communicate among themselves to try stay in sync. If Alice flattens her copy and Bob molds his into a sphere, in no time (bounded by the speed of light and the Internet conditions) they will both see their copies flattened and sphere-like. The copies of magical sand are “telepathic”.

Flattened and sphere-like, that’s impossible! You thought. These actions are in total conflict! Nothing looks flat and like a ball at the same time.

Herein lies the source of magic: **C**onflict-free. The magical sand has built-in rules, or so called “conflict resolution strategies”, to handle conflict situations automatically. Each copy knows these rules and applies them when hearing from other copies. It is actually misleading, right? It is not that conflicts don’t arise, but any conflict is handled by the telepathic copies quietly and swiftly.

Going back to Alice and Bob’s conundrum The conflict resolution strategy may require the molding to happen before the flattening when they were done concurrently. Therefore, both Alice and Bob’s copies are first molded into a sphere, then flattened. Both of their copies look like a round disk at the end.

More importantly, these conflict resolution strategies do not involve additional communication among the copies, meaning they are coordination-free (check out [part 1](https://www.guiltygyoza.xyz/2024/09/ledgers-to-sandcastles){:target="_blank"} for what this means). This makes CRDTs as fast and responsive as the speed of light and the Internet conditions permit.

There you have it. CRDT is a type of data that exists in replicas and always resolves conflicts automatically. It is the perfect type of data for real-time multiplayer collaboration.

Admiring its magical properties, we decided to do something about it: use it to engineer a new kind of digital material for making decentralized applications.

# CRO: the magical rock
With Topology Protocol, we are proposing a new abstraction called Conflict-free Replicated Object, or **CRO**. The is the new digital material we are engineering.

From the whitepaper: *CROs are composable programmable objects that can be updated in real time concurrently and subscribed to as publish/subscribe (PubSub) groups on open P2P networks*. The next blogpost will dive into P2P networks and elaborate on how CRO behaves on the Internet. In this blogpost, we stick to simple terms.

If CRDT is the magical sand, CRO is the magical rock. Let’s see how this metaphor fares.

Rocks are more **durable** than sand. We design CRO to be immune to Sybil attack. For a blockchain, things go south when more than 66% of the network are bad actors. For a CRO, you can have 99.9% of the network go bad and the good guys are business as usual as long as they are connected through each other. (For the curious, check out [whitepaper](https://paper.topology.gg/){:target="_blank"} section 4.1) This allows CRO to go beyond collaborative scenarios and enable competitive use cases.

Rocks can **form much larger structures** than sand does. A typical sandcastle is less than a meter tall. Medieval stone castles are easily 10 to 40 meters tall. We design CRO to clean up its own history so they remain tight and suitable for making large programs. (For the curious, check out whitepaper section 11)

Rocks are more **expressive** than sand. Remember, every CRDT has their conflict resolution strategies built-in. It is extremely rare for developers to invent new CRDTs; they mostly fit their application needs onto existing CRDTs. With CROs, we invite developers to design custom conflict resolution strategies — your own policy for resolving conflicts of all kinds! This opens up the wild design space of distributed object behavior under concurrent operations. (For the curious, check out whitepaper section 4.2)

Additionally, we aim to have **WASM** (WebAssembly) as the standard runtime for CROs. Think of WASM as a virtual computer that it is super cross-platform: it runs on all modern Web browsers, desktop and mobile operating systems, and embedded systems (such as those microcontrollers in drones). Many programming languages compile to WASM. This means developers can create CROs in their favorite language, and these CROs can run in ubiquity. Finally, CROs are **composable** and **interoperable** (through signaling; check out whitepaper section 5), which is key to enabling rich complex systems.

# Hyperstructure beyond crypto protocols
In 2022, Jacob Horne proposed the popular concept of [*Hyperstructure*](https://jacob.energy/hyperstructures.html){:target="_blank"}: crypto protocols that can run for free and forever, without maintenance, interruption or intermediaries.

The first picture in Jacob’s essay is a drawing by Paolo Soleri. The term “hyperstructure” was presumably borrowed from Paolo Soleri’s work in 1969: [*Arcology, the City in the Image of Man*](https://www.organism.earth/library/document/arcology){:target="_blank"}, where the drawing can be found.

<img src="/assets/babel-iid.png" width="700">
(From *Arcology* (1969), chapter 12 “BABEL IID”)

It should be no surprise that our path of building a distributed system protocol for people to be together and collaborate intersects with theories in architecture and urban planning. CROs are meant to be created for communal needs, spawn at will, populated and constantly reshaped by their communities. They are digital communal places. Theories that help us design places for human habitation and flourish are not UI/UX design principles but architecture and urban planning theories.

In chapter 4 of Arcology, Paolo wrote (bold added by us):

> *Arcologies are architectural organisms of such character and dimensions as to be ecologically relevant. They are that architecture which is the ecology of reflective life. … In such a city, open to the environment, the ecology will be determined by man. It will be an arcology, but it will be an arcology only at the condition of **being hyperstructural**, that is, **being the form of the compassionate life developing within**.*

We can see that “hyperstructure” in its original meaning is quite far from Jacob’s appropriation of it that became associated with unstoppability, free of charge, and credible neutrality (user-agnostic).

<img src="/assets/belle.png" width="700">
(From *Belle* (2021). Image courtesy of Studio Chizu and GKIDS; [source](https://www.vfxvoice.com/discovering-the-voice-of-belle-in-the-virtual-world-of-u){:target="_blank"})

Paolo’s hyperstructure is structure that emerges through ecological principles and is deeply concerned with fostering communal interactions. We are aligned with this philosophy. We expect CROs to form pluralistic and interconnected digital places on the Internet, collaboratively morphed by their inhabitants to meet their needs. We aim for CROs to make the Internet more *agentic*.

Instead of being user-agnostic unstoppable machines churning crypto money, CROs are deeply about the preferences and peculiarities of their users. If the design patterns of smart contracts are heavily capital-centric, we envision the emergent design patterns for CROs to be deeply human-centric.