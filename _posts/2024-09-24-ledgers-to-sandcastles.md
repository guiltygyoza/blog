---
layout: post
title:  "From Ledgers to Sandcastles"
date:   2024-09-24 00:00:00 -0500
categories: idea
published: true
---

<img src="/assets/sandcastle.png" width="700">

This essay is also published on [Topology's Blog](https://blog.topology.gg/from-ledgers-to-sandcastles/){:target="_blank"}. The sandcastle drawing is produced by [Ranyah Al-gubani](https://x.com/ra_algubani){:target="_blank"}.

## 1. The smart contract ink
"If code is law on a blockchain, smart contract is the ink that legislates. The law of a digital space is its digital physics. To create digital spaces that are truly sovereign, we ought to use this ink to legislate its digital physics."

This was the starting point of our investigation in 2021, our *shoshin*. We literally authored physics in [Cairo](https://eprint.iacr.org/2021/1063.pdf){:target="_blank"} smart contracts — Runge-Kutta method for [three body simulation](https://x.com/guiltygyoza/status/1450161069058560000){:target="_blank"}, and Euler method for [rigid body collision](https://x.com/guiltygyoza/status/1452311405437366281){:target="_blank"}.

We built *Isaac* (a constrained four-body system), *MuMu* (compositional logic as “discrete” digital physics), and *Shoshin* (collision between axis-aligned bounding boxes). These 3 experimental games interrogated the affordances and limitations of authoring digital physics in smart contract ink.

However, during that process, we moved progressively offchain and into the [local-first](https://www.inkandswitch.com/local-first/){:target="_blank"} design pattern. Why? Because of an elephant in the room.

## 2. Elephant in the room
There is magic when players feel the presence of one another. Isaac, MuMu, and Shoshin are all multiplayer games but they all lack this magic.

The elephant in the room is that blockchains cannot afford the magic of presence.

Not any particular blockchain either. It comes down to a core tenet shared by the designs of all blockchains. Let’s dive in. And no jargons, simple words only.

If a blockchain is a universe, transactions are events that occurred in this universe. What Satoshi Nakamoto meant by “We propose a solution to the double-spending problem using a peer-to-peer network” in the Bitcoin whitepaper is this: the Bitcoin universe, run by many computers all at once, can decide which events happened before or after other events without relying on a special computer that plays the god of the universe.

Why is this design fundamentally incapable of providing the magic of presence? The answer may be surprising: [the speed of light is slow](https://youtu.be/Mc3tTRkjCvE){:target="_blank"}. In the duration of a computer clock cycle, light merely *crawls* 4 inches.

The speed of light is problematic because players that desire the magic of presence are located many miles away from one another. A blockchain network has nodes spanning the surface of Earth. These nodes must coordinate a lot to decide on the state of their universe. Coordination involves sending lots of messages across the Internet, traveling long distances at a speed that is bounded by the speed of light. Doing lots of coordination leads to lots of waiting for the crawling light.

More coordination leads to longer waits. At a certain point, the wait breaks the magic of presence.

## 3. From ledgers to sandcastles
It is not surprising at all that blockchains cannot provide this magic. Blockchains are not designed to enable presence in the first place. They are ledgers. To this date, the vast majority of blockchain use cases are financial. Decentralized finance is incredible, but we are reaching for a more universal need: to be together and collaborate.

We yearn the freedom of assembly and association. The freedom to declare spaces, summon them, populate them, and terraform them to our liking. To do all this without relying on central intermediaries, their rules, permissions, and artificial scarcities. And to do this with privacy guarantees, in a [grassroot](https://arxiv.org/pdf/2301.04391){:target="_blank"} fashion.

We want to spawn beaches at will and build sandcastles together, while you are in Sao Paulo and I am in Seoul. To do that, the magic of presence is essential. Considering the slow speed of light, we need to find a way to minimize coordination between our computers.

## 4. Merge, merge, merge
How can we minimize coordination? Dream bigger: how can we go completely [coordination-free](https://www.vldb.org/pvldb/vol8/p185-bailis.pdf){:target="_blank"}? What does this even mean?

It means we want to be morphing the same digital sandcastle while being 11600 miles apart in the reality (straight line distance between Sao Paulo and Seoul), and all our computers ever do is exchanging our actions, never going back and forth coordinating to confirm on things.

Simultaneously, your computer tells mine what you did to the sandcastle, and my computer tells yours what I did, and we are done — the sandcastle on your screen looks exactly the same as mine, under 100% guarantee.

Think of this process as merging. You send me your copy of the sandcastle. I merge it with my copy. You also merge the copy I send you. To be coordination-free means the results of your merge and my merge are equivalent. Merge, merge, and merge. We [eventually](https://en.wikipedia.org/wiki/Eventual_consistency){:target="_blank"} see the same thing. We never have to coordinate.

Notice that temporarily, the sandcastle on your screen looks different from mine until our information exchange completes. This is the key: to avoid coordination, we must embrace this temporary divergence. We must embrace a universe that looks temporarily different from observer to observer, and each observer’s view is independently valid on its own.

It’s relativity, baby. It’s more modern.

This is not how it works in blockchain land, where the classical absolute spacetime reigns. If the sandcastle lives on a blockchain, at all times the blockchain recognizes one true version of the sandcastle. If you and I touch it at the same time — you hallowing out its moat and I smoothing its surfaces — we will not see each other’s touches until the next block forms on the blockchain (or [6](https://en.bitcoin.it/wiki/Confirmation){:target="_blank"} blocks after, or [30+](https://developers.circle.com/stablecoins/docs/required-block-confirmations){:target="_blank"}).

If this merge thing sounds simple, make no mistake, it’s incredibly tricky to get right. It requires structuring the sandcastle and doing the merges in very specific ways. It requires the foresight to consider all possible conflicts that can arise in the merging process, and to articulate remedies to every one of them. The remedies must be fair, deterministic, and intuitively reflecting the user intentions.

For those of you in the know, yes, we are referring to conflict-free replicated data type (CRDT). It’s a thought virus that erupts on HackerNews every now and then. For those of you that have never heard of it, welcome to the ride. CRDTs are magical materials. To build digital sandcastles with the magic of presence, we need the magical sand. [Topology Protocol](https://paper.topology.gg/){:target="_blank"} is built on the magical materiality of CRDTs, which we are diving into next.