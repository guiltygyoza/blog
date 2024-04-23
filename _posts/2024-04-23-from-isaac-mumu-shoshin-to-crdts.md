---
layout: post
title:  "From Isaac, Mumu, Shoshin, to CRDTs"
date:   2024-04-23 00:00:00 -0500
categories: idea
published: true
---

Special thanks to [Rob Morris](https://twitter.com/recipromancer){:target="_blank"} and [James Addison](https://twitter.com/JungleSilicon){:target="_blank"} for insightful pointers.

This essay captures the first presentation given at [Autonomous Anonymous 2024](https://aaworlds.com/){:target="_blank"} in Lisbon. The video recording is available [here](https://www.youtube.com/watch?v=ybYrJ5amDYc&ab_channel=AutonomousAnonymous){:target="_blank"}.

Topology's founding vision is to create sovereign, persistent, and interoperable realities on the Internet. We considered programmable blockchains as the best foundations for building these realities. At 2021, many design patterns had emerged for onchain financial applications, but very few had been concerned with onchain simulations in 2D or 3D that are multiplayer, interactive, and malleable like our reality. The challenge, therefore, involved a technical part and a creative part. What affordances do blockchains provide, or what can they possibly provide with architectural innovations? That was the technical part. Given the affordances, among the possible realities that can be constructed with them, what are the ones that are deeply human and engaging to be worth our time? That was the creative part.

<img src="/assets/2024-04-23/vision-min.png"/>

We believed that beautiful answers exist and we were motivated to discover them – through experimentation.

<br>
## Isaac

Numerical simulation is the foundation of game physics. For sovereign, therefore inter-objective, realities, their physics must be tamper-proof. Isaac was our first experimental game. Its design centers around a constrained four-body simulation that runs in a Cairo smart contract [1]. Its game mechanics was explained in detail in a past [post](https://www.guiltygyoza.xyz/2022/05/topology-isaac-defcon){:target="_blank"}.

As an execution environment, blockchain is unwieldy. The raw game experience suffered from unstable tick interval which was the block time. Computation-wise, the complexity of the simulation function was limited by block gas limit; in theory it was possible to spread out a simulation run across multiple transactions, one per block, with intermediate states saved between consecutive transactions. Yet at that time gas metering on Starknet was not available. The idea of spending multiple full blocks worth of gas for one single game tick was worrisome.

At the level of player coordination, we observed that most coordination effort happened on a Discord channel. We noted the importance of copresence as the foundation for collaboration and coordination.

<img src="/assets/2024-04-23/isaac-min.png"/>

<br>
## Mumu

We decided to take the block time out of the equation of game experience by implementing "local-first" game mechanics. The concept coincided with the local-first software principle [2], but at that time we have not learned of its existence. Mumu was our second experimental game, designed to be a simulation puzzle to be solved in trial-and-error locally. Only solutions that the players are happy with are voluntarily submitted onchain. We implemented the simulation logic twice, once in Cairo that runs onchain for verification and ranking, and once in Typescript that runs locally in the player's browser.

Game design-wise, we explored giving players a visual programming interface to specify behaviors. We wanted to explore design patterns that allow participants of a malleable reality to "program" the reality in accessible ways. We saw first-hand how players were able to engineer beautiful combinatorics from relatively simple rulesets.

<img src="/assets/2024-04-23/mumu-min.png"/>

<br>
## Shoshin

Shoshin was a "local-first" fighting game. While actual fighting games have players interact in real time, a local-first fighting game asks players to design and submit fighting behaviors, which enter fighting simulations with other submitted behaviors.

<img src="/assets/2024-04-23/shoshin-1-min.png"/>

In some sense, Shoshin was an "upgrade" to Mumu. Instead of solving static puzzles as in Mumu, Shoshin players submitted "solutions" that were measured against other solutions in interactive simulations, which effectively put psychology into gameplay. Shoshin's visual programming interface was much more expressive than Mumu's. Details about Shoshin's design were covered in another past [post](https://www.guiltygyoza.xyz/2023/08/shoshin){:target="_blank"}.

<img src="/assets/2024-04-23/shoshin-2-min.png"/>

In-person playtests were held, once in Paris for PvE mode, and once in California as a PvP tournament. We noticed how much spark and engagement were generated spontaneously in the physical spaces where playtesters were present.

<img src="/assets/2024-04-23/shoshin-3-min.png"/>

During the PvP tournament, we explored concepts around projectile attacks (~hadouken) and king-of-the-hill mechanics (proposed by [Non](https://twitter.com/0xNonCents){:target="_blank"}; to be explained in a future post). Yet it was at that juncture that we decided to explore an entirely different avenue for running programs trustlessly over peer-to-peer networks.

<img src="/assets/2024-04-23/shoshin-4-min.png"/>

<br>
## Problems

Among the three vertices of the blockchain trilemma, decentralization and security are non-negotiable for self-sovereign realities. Blockchains that maximize these two properties suffer in scalability. Yet, scalability is key to enabling copresence and malleability by many concurrent users in a shared reality. How to fix this?

<img src="/assets/2024-04-23/trilemma-min.png"/>

The modular thesis for blockchain scaling stacks multiple "application threads" on top of a shared "parent thread". However, each application thread is still a single thread. A decentralized sequencer seeks to reach consensus among a decentralized network of nodes on a total ordering (sequence) of events, which pays a heavy communication cost to coordination over the Internet. On the other hand, advocates for verifiable computing propose the idea of "zk servers", or centralized sequencers that submit serialized program states in the form of proof-carrying data to the underlying parent chain. This approach introduces liveness bottleneck and vulnerability to censorship.

<img src="/assets/2024-04-23/modular-min.png"/>

To construct *a general-purpose medium* that achieves copresence and highly concurrent malleability for reality-making or autonomous worlding [3], we must look beyond the blockchain paradigm and the trilemma that limits it.

## CRDTs

We heard about CRDTs through a call with [mconcat](https://twitter.com/monoidconcat){:target="_blank"} in the Cosmos ecosystem, where the context was multi-party programmable state channels. Following the call we fell into the CRDT rabbit hole.

In 2006, the web-based text editor Writerly was acquired by Google. It soon turned into Google Doc. Its collaborative editing function used Operational Transformation (OT), an approach that was proposed in 1989 [4], formalized in 1995 [5], and improved by researchers over many years. Its general idea is as follows. Replicate a document into many user copies or replicas. A user can view and mutate its own replica in a *non-blocking* manner. Changes at one replica are propagated to all other replicas. Incoming changes are transformed then applied to the local replica. The transformation step is meant to ensure document consistency. Conceptually I like to analogize OT to [Lorentz Transformation](https://en.wikipedia.org/wiki/Lorentz_transformation){:target="_blank"}, which is the transformation of physical quantities between observer frames whose relative velocities are non-negligible with respect to the speed of light.

<img src="/assets/2024-04-23/google-doc-min.png"/>

The Wave Protocol (developed alongside Google Wave, which was shut down in 2012; [this article](https://jamey.thesharps.us/2018/02/16/how-not-to-replace-email/){:target="_blank"} offers a wonderful recap of its original motivations) used OT to preserve consistency of wavelet data across the users that are sharing the same wavelet from different wave servers connected in a federation model [6,7]. As with all protocols that did not get adopted as broadly as they intended, there were many reasons behind the downfall of the Wave Protocol. Among those, some technical ones were that OT was complex to get right and it still needed centralized servers. Together, these reasons limit the protocol's extensibility and scalability.

<img src="/assets/2024-04-23/google-wave-min.png"/>

Around the same time, researchers were proposing peer-to-peer collaborative editor algorithms *without* OT [8]. This line of work eventually became formalized into Convergence/Commutative Replicated Data Types, which then coalesced into Conflict-free Replicated Data Types (CRDTs) [9]. In short, CRDTs are "multiplayer data types". Each replica of a CRDT records extra "spacetime" metadata with every operation performed so that any two valid replica states are always mergeable into another valid replica state. This property allows for distributed execution without coordination [10].

<img src="/assets/2024-04-23/woot-min.png"/>

<img src="/assets/2024-04-23/crdt-min.png"/>

Throughout 2010s and early 2020s, improvements were made around the issues of composing and garbage-collecting CRDTs, allowing CRDTs to be deployed in production software. Geo-replicated databases use CRDT for state synchronization [11]. Code editors use CRDT to support collaborative teletype [12,13]. Apple Notes uses CRDT for synchronizing across devices. The work on Merkle-CRDT [14] (transporting CRDT updates in a Merkle DAG) spawned peer-to-peer database solutions [15].

<img src="/assets/2024-04-23/production-min.png"/>

On the day we fell into the CRDT rabbit hole, despite CRDT's origin in collaborative document editing, one thing was instantly clear: the difference between collaborative editing and multiplayer interactive simulations, particularly those without stringent timing constraints, is only an increase in dimension. Multiple users typing into the same document positions is not unlike rigid bodies attempting to move into the same coordinates in space.

Few had considered using CRDTs for making games. From our own survey and from communication with Martin Kleppmann, author of BFT-CRDT [16], we only know of one academic work that considered the intersection of peer-to-peer CRDT and videogames [17]. We also came across the work by James Addison and Rob Morris on a tiny Minecraft implementation with CRDTs [18].

To prove our intuition, we used [Yjs](https://github.com/yjs/yjs){:target="_blank"} to construct a peer-to-peer multiplayer platformer prototype where each log-in user controls a penguin character and operates at 60 frames per second. CRDTs were used to represent and synchronize the state of the game world. WebRTC was used as the network transport.

<img src="/assets/2024-04-23/penguin-1-shortened.gif"/>

Later, as a proof of concept for collision resolution, we endowed each user with a CRDT mailbox so that users can request one another to back off when intersection occurs.

<img src="/assets/2024-04-23/penguin-2-shortened.gif"/>

The source code is available [here](https://github.com/topology-gg/esotere-client){:target="_blank"}. Note that the prototype was not tolerant to Byzantine faults and did not preserve causal ordering among operations.

## Topology Protocol in a nutshell

The goal of Topology protocol is to create a general-purpose medium for anyone to construct self-sovereign malleable realities on the Internet, and to experience copresence in them. In a nutshell, the protocol is based on the following architectural concept: user-defined BFT-CRDT actors running over a peer-to-peer network that functions like a "random access memory" for the world computer. Explanations are left to the next post.

### Reference

[1] Goldberg et. al., Cairo – a Turing-complete STARK-friendly CPU architecture, 2021. [link](https://eprint.iacr.org/2021/1063.pdf){:target="_blank"}

[2] Kleppmann et. al., Local-first software – You own your data, in spite of the cloud, 2019. [link](https://www.inkandswitch.com/local-first/){:target="_blank"}

[3] ludens, Autonomous Worlds (Part 1), 2022. [link](https://0xparc.org/blog/autonomous-worlds){:target="_blank"}

[4] Ellis et. al., Concurrency Control in Groupware Systems, 1989. [link](https://dl.acm.org/doi/pdf/10.1145/67544.66963){:target="_blank"}

[5] Nichols et. al., High-Latency, Low-Bandwidth Windowing in the Jupiter Collaboration System, 1995. [link](https://dl.acm.org/doi/pdf/10.1145/215585.215706){:target="_blank"}

[6] Wang et. al., Google Wave Operational Transformation, 2010. [link](https://svn.apache.org/repos/asf/incubator/wave/whitepapers/operational-transform/operational-transform.html){:target="_blank"}

[7] Gregorio, Google Wave, 2009. [link](https://www.usenix.org/legacy/event/lisa09/tech/slides/berlin.pdf){:target="_blank"}

[8] Oster et. al., Real time group editors without Operational transformation, 2005. [link](https://inria.hal.science/inria-00071240/document){:target="_blank"}

[9] Shapiro et. al., Conflict-free Replicated Data Types, 2011. [link](https://pages.lip6.fr/Marc.Shapiro/papers/RR-7687.pdf){:target="_blank"}

[10] Bailis et. al., Coordination Avoidance in Database Systems, 2014. [link](https://www.vldb.org/pvldb/vol8/p185-bailis.pdf){:target="_blank"}

[11] Active-Active geo-distribution. [link](https://redis.io/active-active/){:target="_blank"}

[12] Atom's teletype-crdt. [link](https://github.com/atom/teletype-crdt){:target="_blank"}

[13] Jahns, How we made Jupyter Notebooks collaborative with Yjs, 2021. [link](https://blog.jupyter.org/how-we-made-jupyter-notebooks-collaborative-with-yjs-b8dff6a9d8af){:target="_blank"}

[14] Sanjuán et. al., Merkle-CRDTs – Merkle-DAGs meet CRDTs, 2020. [link](https://research.protocol.ai/publications/merkle-crdts-merkle-dags-meet-crdts/psaras2020.pdf){:target="_blank"}

[15] OrbitDB. [link](https://github.com/orbitdb/orbitdb){:target="_blank"}

[16] Kleppmann et. al., Making CRDTs Byzantine Fault Tolerant, 2022. [link](https://martin.kleppmann.com/papers/bft-crdt-papoc22.pdf){:target="_blank"}

[17] van der Linde et. al., Practical Client-side Replication: Weak Consistency Semantics for Insecure Settings, 2020. [link](https://www.vldb.org/pvldb/vol13/p2590-linde.pdf){:target="_blank"}

[18] Addison & Morris, "Metaverse in a box" demo, 2022. [link](https://twitter.com/JungleSilicon/status/1590645640325103616){:target="_blank"}
