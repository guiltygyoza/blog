---
layout: post
title:  "Civilizational Computing"
date:   2022-09-12 00:00:00 -0500
categories: crypto
published: true
---

ELI5: Desktops, laptops, smartphones etc belong to personal computing - they compute for our personal benefits. The blockchain represents civilizational computing - it computes for collective civlizational interests.

This essay is an exerpt from Topology's whitepaper still in draft.

A decade has passed since Satoshi Nakamoto introduced Bitcoin to the world, yet with multiple cycles of busting hopes in mass adoption, the value of blockchain to the general public remains questionable. It is obvious that Bitcoin is the first hard drive for the human race, while Ethereum is the first mainframe computer for the human race. They achieve resistance to state level attacks through radical decentralization, and achieve security through clever and evolving consensus mechanisms. Despite analagous to hard drive and mainframe, apparently their purpose to the human race is radically different from why the first hard drives and mainframe computers were invented in 1950s. False characterisation of what blockchain is and what it is most valuable for is the reason behind busting hopes and misallocated resources.

The first hard drives and mainframe computers were invented in the movement of automating computation: given some initial knowledge represented in algebra, and some axioms of interest also represented in algebra, we wish to derive implied knowledge automatically. For example, John's platoon learns the position of the enemy company, and understands the rules of parabola as well as the initial velocity of their mortar shell. John can calculate where their shell trajectory intersects with the ground given a certain angle for their mortar setup, and by carrying out inverse calculation, John can obtain the angle of their mortar setup such that the shell trajectory intersects with enemy position precisely. Computing used to be generally manual, with special procedures to compute specific arithmetic operations such as square roots and exponentials. With Kurt Gödel's finding, we understood we could represent a huge class of human logical statements in pure arithemtic, making them susceptible to arithmetic manipulation, which is rich, precise, and is susceptible to automation. With Alan Turing's work, we understood we could construct Turing machines, which are universal computing machines that can compute a large class of problems. With John von Neumann's work, we understood we could practically build these machines using electronics and make them programmable. The von Neumann architecture and Harvard architecture popularized the notion of memory storing programs to be computed. Soon after, hard drive was invented to securely store data to be computed by computers, and mainframe was invented to concentrate computing power, accessible first through punchcards and linear job batching.

The essence of blockchain is not about automating computation, but automating verifiable computation. The effective computing power of Ethereum does not rival that of a modern smartphone. Blockchain is not meant for personal computing, but for specific kinds of computing that serves new kinds of collective interests - interests that surpass national borders - by maximizing the protection of individual interests. For example, borderless banking systems such as MakerDAO are possible because blockchain automates credit and debit operations atomically and verifiably - verifiable by anyone that runs a low-requirement light client - such that counterparty risk is eliminated. Early blockchain systems achieve verifiability through massive redundancy. With the advent of fraud proofs and validity proofs, we understood we could achieve efficient verification while retaining strong decentralization - intead of increasing the computer power of verifier machines, we reduce the complexity of verification. Fraud proofs achieve this by game theoretic setup, while validity proofs achieve this by verification in sublinear complexity, such as STARK proof whose verification complexity is polylogarithmic to the original computation being proven. If we view computation as representation of knowledge, which is the most valuable asset produceable by human, the value of automating verifiable computation is apparent: we can build decentralized knowledge engines that automatically and efficiently verify the truthfulness of knowledge as well as compute the characteristics of such knowledge, while remaining resistant to nation-state internvention. We can build systems that mediate the creation, access, and modification of computable knowledge (Stephen Wolfram) across national borders. For example, Park wants to solicit the solution to a high-stake cryptography problem. Park can write the verification procedure of solutions to the problem as a smart contract program, and put up a bounty controlled by the same contract to be transferred to the account that first submits a valid solution that passes the verification procedure, all enforced autonomously by the blockchain. With sublinear verification enabled by validity proof systems (e.g. the Cairo CPU), we can afford to tackle problems of much greater complexity, hence making this knowledge engine more broadly useful.