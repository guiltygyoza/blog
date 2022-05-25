---
layout: post
title:  "The verifiable computing stack"
date:   2022-05-24 00:00:00 -0500
categories: crypto
published: true
---

ELI5: As we embark on the next multi-decade super cycle of technology movement, verifiable computing, it is helpful to map out the different layers of abstraction involved for strategic purposes. At Topology we tentatively sketch out the following stack:
- Level 8: Frontends
- Level 7: Hyperstructure & application
- Level 6: Low-level libraries
- Level 5: Programming language & compiler
- Level 4: Arithmetization & architecture
- Level 3: Proof generation & verification
- Level 2: Distributed system
- Level 1: Hardware acceleration

As to why verifiable computing constitutes a technology movement with broad impact, we believe in three essential qualities: unstoppability, immutability, composability. See [this video](https://www.starknet.house/dhrumil-fellows){:target="_blank"} for [Dhrumil](https://twitter.com/wandcrafting){:target="_blank"}'s colorful elaboration.

---

#### Level 8: Frontends
Frontends seem out of place in the stack of verifiable computing at first glance. The key here is to recognize the underexplored advantage of running proof generation on the client side.
<br/><br/>

#### Level 7: Hyperstructure & application
This is where the next waves of developers and creators will participate directly in. For definition, see [Hyperstructures](https://jacob.energy/hyperstructures.html){:target="_blank"}.
<br/><br/>

#### Level 6: Low-level libraries
This is where the semblance of numpy, scipy, onnx belong. For example, see [Giza](https://twitter.com/gizatechxyz){:target="_blank"}.
<br/><br/>

#### Level 5: Programming language & compiler
This is where the programs / design intent written in accessible and ergonomic notations at Level 5-7 are transformed into standardized objects (e.g. with respect to some instruction set architectures) that are susceptible to arithmetization. For example, see [Cairo](https://eprint.iacr.org/2021/1063.pdf){:target="_blank"} and [Risc0](https://github.com/risc0/risc0){:target="_blank"}.
<br/><br/>

#### Level 4: Arithmetization & architecture
This is where standardized objects from Level 5 are transformed into polynomial constraints. For example, see [ethSTARK](https://eprint.iacr.org/2021/582.pdf){:target="_blank"}.
<br/><br/>

#### Level 3: Proof generation & verification
This is where polynomial constraints are transformed into (succint, zero-knowledge) proofs that can be (efficiently, recursively) verified, where the qualifiers in parenthesis are metrics to strive for. For example, see [DEEP-FRI](https://arxiv.org/pdf/1903.12243.pdf){:target="_blank"} and [KZG](https://www.iacr.org/archive/asiacrypt2010/6477178/6477178.pdf){:target="_blank"}.
<br/><br/>

#### Level 2: Distributed system
This is where the design of blockchain or rollup system architecture belong. For example, see [StarkNet Decentralization](https://community.starknet.io/t/starknet-decentralization-tendermint-based-suggestion/998){:target="_blank"}.
<br/><br/>

#### Level 1: Hardware acceleration
Self explanatory. For example, see [Ingonyama](https://www.ingonyama.com/){:target="_blank"}.