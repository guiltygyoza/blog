---
layout: post
title:  "Hyperstructures on ZK Rollup"
date:   2022-02-17 00:00:00 -0500
categories: crypto
published: true
---

1- Open source software is beautiful. Human capital and productivity is the driving force of civilization advancement. Blockchain is a place where credible neutral mechanisms are formalized and enforced. It would be impactful if we could design ways to leverage the blockchain to formalize and enforce mechanism through which open source software accrues value, improving social scalability ([Nick Szabo](http://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html)) which drives human productivity, the highest leverage to accelerate civilization advancement.

2- Here let us limit the discussion to public goods smart contracts on ZK rollup, either validity or private. By providing verifiable heavy computation and privacy, which will enable a series of high-impact application genres, it is reasonable to deduce that a large portion of the hyperstructures ([Jacob Horne](https://jacob.energy/hyperstructures.html)) will be on ZK rollup.

3- As ZK rollup is just becoming operational at 2022, it is the perfect time to conceptualize a better way to support public goods L2 smart contracts.

4- What are some interesting examples for public goods smart contracts that are L2-native? One example would be to write a set of smart contracts that perform popular sampling algorithms efficiently. Another example would be to write a set of smart contracts that perform intersection tests, one of which may be between a circle and a convex polygon.

5- How does a public goods smart contract accrue value? A first order solution would be to set up a paywall on the contract level: contract A calls a function in contract B which is public goods, contract A pays X ETH to an address designated by contract B, otherwise the transaction is reverted. A variation of this would be a subscription model using a non-fungible token. Imagine a NFT called FP32, which represents the subscription to the 32-bit floating point library smart contracts on L2. Holding FP32 requires paying X ETH to an address designated by the L2 library smart contracts every Y L1 blocks.

6- The weakness of these approaches is apparent: one could easily take the public goods smart contracts, remove the paywall logic, and redeploy them. Still, it can be argue that the ecosystem of paywalled public goods smart contracts could attract and retain a roster of higher quality projects, because (1) they are better maintained, and (2) they are better culturally aligned.

7- Still, can we do better? Is there a way through which smart contract library developers have the confidence knowing their work will be attributed fairly and will accrue value in ways that are enforced credibly neutrally?

8- One potential solution is: to go one level deeper from the contract level to the blockchain level. We know that value accrual logic is prone to removal through contract redeployment, which is low effort. If the logic is enforced at the blockchain level, through fee mechanism, it has a stronger moat.

9- If we carve out 5% of a ZK rollup's fee towards public goods smart contract funding, and we design collectively a mechanism through which value accrues across a chain of contract calls based on metrics such as value-weighted traffic (an application contract may call a higher level library contract which calls a lower level library contract), the said ZK rollup could become the unique place where hyperstructure builders can build sustainbly, knowing that they are guaranteed to capture value when their library is proven useful to the higher level libraries and applications.

10- Note that it is very difficult to do it with Ethereum, even if it is culturally aligned with this approach, given the stakes involved to change anything at the protocol level. It is many orders of magnitude easier to drive the implementation of this with a ZK rollup at 2022, when fee mechanism is just being designed.

11- Note also that there are at least two approaches to implement this, and perhaps we need both. (1) If a library contract is deployed immutably - no proxy pattern, @view only - then value accrues to it directly. If a library contract is imported by a higher-level contract, we need the rollup to parse the contracts at compile/deployment time and insert the corresponding value accrual logic. I prefer the first approach which helps alleviate state bloat, although the cross-contract call syntax is less convenient. To address that we can add syntactic sugar for easier cross-contract calls.