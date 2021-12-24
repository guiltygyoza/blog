---
layout: post
title:  "Game studio notes"
date:   2021-10-04 00:00:00 -0500
categories: game
published: false
---

1. Decentralized Autonomous Game
- has eth
- accept donation
- accept staking to profit-share

2. Fully on-chain generative game
- DAG contracts - running DAG logic; get updated algs from trainer
- Trainer contracts - running training algs based on data provided by DAG

3. Game mechanics
- surrounding a mathematical truth which manifests itself as seemingly random phenomena in game  
- players can leverage their correct prediction of the phenomena to gain upper hand
- the phenomena is proved (via zkp?) to be deterministic, and perhaps closed-form
- the game ends when the truth is discovered.

4. On-chain numerical physics / universe simulation**
- ODE => python script => generated stateless cairo function
- I think that the heavy use of PRNG is to create an illusory complexity of the universe without having to deal with the complexity itself. On-chain physics simulation changes this by running an actual complex physics engine on the universal computer, while keeping the core numerical codes completely hidden, just like how the "physics laws" are hidden in our universe hence our scientific endeavors to model the observable phenomena.

===

Cairo experiment 1: on-chain RL tic-tac-toe agent
- Trained Q-table via python RL script
- Convert Q-table lookup operation to Cairo program using the dictionary data structure in Cairo Common Library.
- Simple frontend for visualization and interfacing with the StarkNet contract.

Cairo experiment 2: on-chain Runge-Kutta method (RK4)

Cairo experiment 3: on-chain three body problem using Hamiltonian Neural Network (NN + RK4)
- three body motion dictated by on-chain numerical analysis
- whenever states are viewed from external, random noise is added as measurement noise
- use HNN to preserve law of conservation
  - => use its bijective property for calculating backprop (for constructing S vector) without storing activations *see HNN references
  - we can add/remove energy and see the system mutate!
