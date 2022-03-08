---
layout: post
title:  "The ELI-5/ELI-15 principle at Topology"
date:   2022-03-07 00:00:00 -0500
categories: crypto
published: true
---

Special thanks to Alan Luo, Daniel Hong, Sina Habibian, Alok Vasudev, and as always, Kunho Kim, for inspirations.

1- I cofounded Topology with Kunho Kim (prev: Harvard, EF, Mainstreet Investments) to shape the future of zk rollup ecosystem.

2- To achieve reflexivity in long term innovative work, it is important to identify and leverage the fundamental properties and distinguishing strengths of the medium we work with. The medium we work with is the combination of smart contract development using highly expressive language such as Cairo, invented by StarkWare Industries, and the design of zero knowledge proof systems optimized for performant proving and verification of specific families of computations.

3- Broadly, we have identified two properties of our medium: (a) composability/interoperability, and (b) recursive specialization for verifiable heavy/exotic computations. The former points to the key potential of working with a global state machine: shared toolings composable through standardized interfaces / traits, which in other mediums is practically impossible or nonexistent. The latter points to the key potential of zero knowledge rollups: specialized higher-level rollups submitting proofs downward to lower-level rollups for verification and settlement. StarkWare refers to this vision as fractal scaling. Indeed, above L2, the topology of rollups will look less like lasagna and more like romanesco.

4- With these properties, Topology makes two conjectures: (a) applications built on zk rollups will benefit from strong [social scalability](http://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html){:target="_blank"} (per Nick Szabo) - as a metaphor, we can achieve the generalization of Dark Forest's plugin mechanism to all applications, where players/users and developers are one, collectively expanding the boundary of application utility and use cases, or the boundary of play in onchain games. (b) zk rollups will transform domains that seem utterly irrelevant to distributed ledger technologies now; one such possibility is laid out in [Decentralizing patent offices](https://www.guiltygyoza.xyz/2022/02/decentralized-innovation-protocol){:target="_blank"}.

5- Topology envisions working across many disciplines - cryptography, formal verification, programming language/DSL, scientific computing, game design - to drive the growth and impact of zk rollup ecosystem. Yet we are cognizant of the challenge in working across multiple disciplines.

6- At 2022, research domains have specialized tremendously such that cross-domain communication of the latest findings and unsolved problems is very difficult. This can be observed from society at large - large swaths of populations are oblivious to the latest findings in longevity research, quantum computing research, defi protocol research etc, all of which intimately characterizes our future civilization capability. With our ambition to work across disciplines, it is important to develop the right communication framework such that our colleagues and partners can effectively compound our collective knowledge, aggregating first-principle thinkings to drive decision making, which we intend to make ridiculously agile.

7- The 6-pager rule, created by Amazon, is an effective narrative structure for driving decision making. However, we recognize the speed with which the crypto industry evolves particularly at the bleeding edge of validity rollups, making long form formal communication an inefficient tool. Furthermore, rigorous data & logic-driven decision making may be at odds with our priority of maximizing creative freedom for our colleagues and decentralizing decision making - sometimes, valuable intuition is not backable by solid data or pure logic; enforcing the use of data and hard logic for proving the value (soundness, feasibility etc) of ideas seems to suit centralized/hierarchical decision making in industries where metrics are well defined and optimization reins more so than decentralized decision making in small agile teams exploring open-ended directions in fast-evolving industries.

8- Yet, lacking structure in communication is akin to running a slack or discord server with very loose channel-specific rules. A middle ground must be found.

9- We recognize the value of ELI-5 (explain-like-I-am-five) single-paragraph descriptions. It forces the ideator to reach the core argument of her insight and find the most effective and succint mental model or metaphor possible for understanding such insight. Besides the insight itself, it is valuable to delineate the context where the insight is situated or applicable.

10- In order to balance the danger of using abstract metaphoric language in ELI-5, we coin ELI-15 (explain-like-I-am-fifteen) as an additional level-of-detail (LOD, borrowed from rendering techniques) that expands ELI-5's single-paragraph description into a short coherent sequence of paragraphs that is akin to a thread of tweets. Finally, we retain the 6-pager narrative format as the highest LOD.

11- Additionally, visualization is preferrable when the insight features parallelism or nonlinearity that is hard to articulate with words but trivial to convey in images.

12- Thus, we can formalize the unit of communication for an insight at Topology into the following struct definition, in pseudo-Cairo syntax:
```

  struct Insight:
      member ELI-5 : ShortParagraph
      member ELI-15 : ShortThread
      member ELI-40 (optional) : SixPager
      member Visualisation (optional) : Schematics
  end

  # assert_le (Paragraphs_len, 10)
  struct ShortThread:
      member Paragraphs_len : felt
      member Paragraphs : ShortParagraph*
  end

```

