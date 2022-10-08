---
layout: post
title:  "Civilizational computing for computable knowledge"
date:   2022-10-08 00:00:00 -0500
categories: crypto
published: true
---

Summary: Civilizational computing, far from being the most performant computing platform but certainly the most legitimate one, is suitable for programmatically manage the rights and obligations of computable knowledge. Coupling privacy tech with civilizational computing, the inventors of computable knowledge could have the cakes and eat them too.

(For context on Civilizational computing, see the previous [post](https://www.guiltygyoza.xyz/2022/09/civilizational-computing))

1- Mischaracterization of privacy: the narrative of "giving people total control over their privacy, computing environment, data ownership" is grossly misled. The essence of blockchain computing, coupled with privacy technologies, is more about slaying molochs to resuscitate our civilization from post-industrial post-modern swamp and accelerate human progress.

2- It is well known that a "bad" Nash equilibrium persists when the creator of an intellectual property has to choose between "publicizing the intellectual property at the loss of downstream personal financial returns" or "keeping the intellectual property secret, yet depriving its potential values to others."

3- The tower of human knowledge is created by knowledge composition. For example, by composing the knowledge of building a telescope and the knowledge of precise plotting through mechanical apparatus, Copernicus produced the knowledge of celestial body moving in ways inconsistent with what the Church asserted. Human progress slows down when knowledge composition is hindered.

4- With zero knowledge proofs, and restricting ourselves to *computable knowledge* (Stephen Wolfram), we could for the very first time in our history scalably break this bad Nash equilibrium: one could retain exclusive access to a piece of secret computable knowledge while making the knowledge *trustlessly use-ful* to others via private compute. *Inventors of computable knowledge could have the cakes and eat them too.*

5- Further productivity arises when composition is possible, such as through proof recursion and aggregation, which enables composing *N* secret computable knowledge with *M* non-secret computable knowledge. This brings forth the concept of *composable commercial secret* - proprietary computable knowledge composed with other proprietary computable knowledge (each private to a different party) into larger "half-opaque" computable knowledge.

6- For example, Chang knows in the form of CAD files the precise geometry of a rocket nozzle that exhibit certain mechanical properties. Nicholas knows the precise mix of propellants that exhibit certain physical and chemical properties. Jae wishes to simulate the firing of a rocket using Chang's nozzle design and Nicholas's propellant formula to analyze the resulting thrust, fuel efficiency, and mechanical stability. An interactive scheme can be devised to run the firing simulation (a public function) with the rocket geometry (a function private to Chang) and with the propellant formula (a function private to Nicholas), and require Jae to pay fees on-chain to run such public-private simulation. We could call these *composable computable knowledge*.

7- Smart contractual terms (i.e. autonomously enforced) regulating the flow of financial value could be built around the condition of use for each composable computable knowledge. Following the example above, Chang could rate-limit computational access to her secret nozzle design and charge per-access according to some demand curve.

8- *Trustless liveness* through zk proving delegation: what if Chang wants to monetize her secret computable knowledge without either maintaining a high-uptime machine running local zk proving herself, or *trusting* some centralized servers running the zk proving for her that promise not to peek into the secret witness (thereby breaking the secrecy of knowledge)? It is possible to delegate zk proving to an MPC network that preserves the secrecy of the witness [Chiesa, Lehmkuhl, Mishra, Zhang; [talk](https://www.youtube.com/watch?v=iT_s92f3wds&ab_channel=ZeroKnowledge)]. Further research is required to enable dynamic joining/leaving of the MPC network and further reduce complexity blowup.
