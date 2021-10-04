---
layout: post
title:  "Crypto-native Games"
date:   2021-10-04 00:00:00 -0500
categories: crypto
published: true
---

In accordance with gubsheep's [crypto gaming thesis](https://gubsheep.substack.com/p/the-strongest-crypto-gaming-thesis){:target="_blank"}, I propose two directions for crypto-native game development:

#### 1. On-chain Generative Games
Example: an infinite on-chain grid-based dungeon where
- the game starts with a initial boundary expandable by player exploration;
- newly explored grid may contain object/monster which player can interact with;
- the spawning of object/monster and map-wide events are controlled purely by a generative algorithm that lives in the contract;
- rewards are given to player by the contract in the form of NFTs.

#### 2. Autonomous Games.
Example: an autonomous chess contract where
- both EOA & contract are welcome to challenge;
- only one challenger at a time identified by address;
- if challenger does not make its next move for a predefined period of time (e.g. after X L1 blocks), the AI automatically wins;
- the chess board status is public at all time for query; every win/loss condition, a turn-by-turn record and challenger address is recorded in the contract.
- most critically, upon game contract deployment the private key is burnt so that the game is truly autonomous -- no backdoor for any person/contract, which is to say *the game is developer-free upon publication*.

What really intrigues me is what the combination of the two directions above would yield. Example: an autonomous chess contract that auto-rebalances:
- following the autonomous chess contract above, with the addition of an auto-rebalance algorithm that adjusts the difficulty of AI according to the moving average of AI's win rate over the past X games;
- the game would emit erc-20/erc-721 rewards to every winning challenger.

We can further give *health point* to the autonomous game contract. For example:
- following the auto-rebalancing autonomous chess contract, with the addition of a stake-to-challenge mechanism, where every challenger stakes Eth to begin challenge; a successful challenge would yield the challenger X amount of Eth from the contract's balance, while an unsuccessful challenge would cost the challenger the Eth staked.
- the AI is *reversibly dead* when its balance goes to 0; it can be *revived* by infusion of Eth to its balance.

We can further give the autonomous game contract the ability to *learn* from past games:
- when the AI is tuned up to its highest difficulty and still loses more than it wins, it runs its learning algorithm on the recorded turn-by-turn game records to expands its difficulty spectrum;
- this would allow the game contract to extend its lifespan by winning more games and thus more Eth.

This idea coincides with my earlier thinking on [The Autonomous Dimension](https://hchsueh.com/2021/04/decentralized-automata){:target="_blank"}. I believe we are helping to create a new species that live entirely on-chain - a tribute to Primavera De Filippi's [Plantoid](https://plantoid.org/){:target="_blank"} project and the [ArtDAO](https://blog.oceanprotocol.com/artdaos-curation-markets-and-tcrs-2d2847e4a0f9){:target="_blank"} idea by Simon de la Rouviere and Trent McConaghy.
