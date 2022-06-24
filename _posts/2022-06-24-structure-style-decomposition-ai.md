---
layout: post
title:  "Structure vs style decomposition for onchain AI"
date:   2022-06-24 00:00:00 -0500
categories: crypto
published: true
---

ELI5: A richer dimension of UGC is User Generated Behavior (UGB), or in other words user-generated AI. If blockchain were to revolution the game industry, builders on blockchain must tackle the holy grail of games - sophisticated game AI. Topology has conviction towards onchain AI interop and composability towards proliferation of UGB.

### Structure vs style decomposition (SSD)
Chris Hecker asserted in his [GDC lecture in 2008](https://www.chrishecker.com/Structure_vs_Style) that the key to solving any *hard interactive problem* is to find the right structure vs style decomposition (SSD), where "hard interactive problem" is defined as any problem that sits at the intersection of technology, aesthetics, and interactivity. To borrow the wisdom from [category theory](https://bartoszmilewski.com/): human thinks in certain structure, which could be summarized by one concept: *chop and conquer*. For problems that are not practically choppable into smaller problems, human can not reason about them. For problems that lack effective frameworks of chopping and decomposition, human cannot begin to tackle them. Unchoppable problems are intimidating and uninvestible. Choppable problems can be tackled. How to chop a problem is the *structure* in SSD, whereas using that structure to solve the problem is the *style* in SSD.

### Game AI as holy grail, and the lack of SSD for game AI
In the same GDC lecture, Chris Hecker asserted that AI should have had the most profound impact on games but had not - AI technology is the key to deep interactivity, consequence, and meaning. Chris further asserted that the reason for AI not having huge impacts on games was because we had not found the right SSD for game AI. Chris hypothesized the existence of *Photoshop for AI*, with which the process of creating AI does not involve coding. Fast forward to today, despite the proliferation of deep learning research, DRL agents playing complex RTS games competitively, and large language models run by hyperscalers triggering existential debates on AI consciouness, these research has ~0 bearing on the making of any game AI in state of the art AAA titles.

### What is AI?
Note that "AI" here absolutely does *not* mean the popularized & superficial notion of machine learning! It means agents in game worlds that are able to sense, reason, decide, and act autonomously. Robotics is perhaps a fitter term, but I will stick to AI because robotics is a mouthful. Below is a classic characterization of AI from [Russel & Norvig's textbook](https://en.wikipedia.org/wiki/Artificial_Intelligence:_A_Modern_Approach). In essence, AI constitues sensing, intentionality, decision making, and acting within an environment that can be sensed, reasoned about, and acted upon.

<img src="/assets/russel_norvig_ai.png"/>

### Solve the hardest problem
Our mentality at Topology is: if scalable blockchain were to transform the game industry, it must tackle the hardest challenge faced by the industry. We must think in leaps, not increments. Some thoughts here:

1. In essence, blockchain is not a database (it's a horrible storage medium!), but a credibly neutral enforcer of computation. The emergence of validity proof systems further accentuates this fact.
2. If database is not the essence of blockchain, using blockchain as records of hex/byte strings that have meaning offchain is a drastic under-realization of its potential.
3. If AI is the future of game, we must explore blockchain as a potential way to bring about that future.
4. Sophisticated AI enrich game worlds. Topology holds a creative-centric stance towards building onchain realities, which naturally leads to our conviction in AI interoperability and composability.
4. The goal of AI interoperability is to achieve standardized computational models that manifest the sensing, reasoning, decision making, and acting components of AI, such that *any* reality compatible to such standard models would be able to host these AIs i.e. allowing AI to traverse across different realities. Why interoperability? Because interop shifts the power dynamics towards the creators (see [Behavior interoperability](https://www.guiltygyoza.xyz/2022/06/behavior-interop)).
5. The goal of AI composability is to create the "Photoshop for AI" that enables expressive composability of AI - composing fragments of intentionality into richer intentionality, and composing micro behaviors into more complex behaviors. Why composability? It boost expressivity and productivity, and is equivalent to the notions of function compositionality, modularity, and separation of concerns. With composability, we can build bigger, richer, more sophisticated, and safer systems.
5. Thus far the privleged joy of creating game AIs is restricted to game designers, or specifically the AI engineers and designers in game studios. Being creator-centric means Topology believes in *finding the SSD that allows for democratization of AI creation*. Some anecdotal evidence: in 2022, there are ~300k employees in the US game industry, which accounts for ~0.1% of US population; there are 60%+ US population that identify themselves as gamers. Being creator-centric means "going from game 1.0 to game 2.0": making games massively and deeply writeable, not merely readable/consumable.
6. Put in another way, we at Topology are hypothesizing the proliferation of a new dimension of UGC: User Generated Behavior (UGB) on-chain, and its pivotal role in allowing for continuous evolution and deepening of onchain realities.

### Onchain Game AI SSD v0.1
Our earliest attempt at game AI SSD, using a prototyped onchain 2D fighting game as the concrete targeted context, yielded the following structure for computing agent behavior in a loop:

```

  Variables:
  - PHY: the raw states of the game world, primarily consisting of object dynamics / hitboxes
  - A: the internal state of the agent
  - C: the state of the character in character state machine
  - p: the perceptibles produced by the agent's sensors
  - a: the actions that the agent intends to perform
  - s: the stimuli to the agent computed from physicality

  Loop:
    // 1. Perceive from physicality
    Perception : PHY => p

    // 2. Compute intentionality and decision making for agent
    Agency: A, p => A', a

    // 3. Compute character state transition
    Character: C, a, s => C'

    // 4. Compute consequences in physicality
    Physicality: PHY, C => PHY', s

```

In terms of agency modeling, our earliest prototype uses *finite state machines* to model the computation of intentionality and uses *behavior trees* to model the process of behavior selection, which is deeply inspired by the HFSMBTH model introduced by Bobby Anguelov in a [GDC talk in 2017](https://ubm-twvideo01.s3.amazonaws.com/o1/vault/gdc2017/Presentations/Vehkala_AI%20Arborist.pdf), banking on the promise of composability with these constructs. Furthermore, the prototype implements the popular input mechanics of "input buffer" in fighting games, which allows the player to queue up actions to be performed by the character at its next earliest availability. The use of input buffer is somewhat analogous to the "sequential" control node in game behavior trees; we believe the input buffer mechanic presents a more elegant solution for manipulating sequences of actions intended by the agent to be performed.

The publicized [demo sequence](https://twitter.com/guiltygyoza/status/1539696376870838278) was created with the following trivial agent model:
<img src="/assets/early_demo_agent.png"/>
