---
layout: post
title:  "Max Hodak - notes"
date:   2021-10-04 00:00:00 -0500
categories: game
published: false
---

Video game design is challenging on multiple levels. Scripted worlds may be engaging for a short period of time, but ultimately suffer from the limited hand-crafted information embedded by the developers for the player to experience. It is possible to build open sandbox worlds that support a great degree of creative expression (for example, Minecraft or SimCity), but game mechanic design is a difficult art. Most variations are neither engaging nor fun, and all of them are characterized by severe limits to their depth.

It’s often been observed that immersion in virtual worlds is far more related to psychological and emotional depth than graphical fidelity.[1] It is an important point that in considering the physics of a simulated reality, we are not principally concerned with the quality of the graphics, though presumably they would follow as “for free.” **We are principally concerned with the range and sophistication of the emotionally satisfying creativity that the world supports.**

We can of course do any of these things by writing additional logic into the game engine. It is easy to see, though, that the complexity of this problem grows very quickly with the depth of the world. ... The devoted game developer can add a huge number of rules to their engine to get any specific desired behavior, but the problem of getting broadly general emergent behavior in circumstances not specifically imagined by the developer quickly becomes an intricate theoretical challenge.

The richness of the world as enabled by its physics is of central importance in building a world that is as richly creative, or more so, as our base reality. In lieu of a good theoretical motivation for such a physics system, games will remain comparatively shallow and unrewarding over a long enough timescale.

[遊戲世界複雜度 = f(遊戲開發方式, 資金/資源); 傳統遊戲開發方式導致產出複雜度為投入資金/資源的log()，AAA 遊戲複雜度若要再提升，要投入指數倍更多的資源，以現行遊戲公司商業模式而言不實際。我的工作室若能產出“發布後即無人管理、複雜度自動生成”的遊戲，則理論上讓我的開發方式能產出複雜度為投入資金資源的線性或甚至指數。借鏡：No Man's Sky，只做視覺層次的複雜度沒有觸及 expanding range of creative expression]

[需要 formalize 一個虛擬世界的 “depth”。]

[隨手估計：US Department of Energy's Jefferson Lab 估計地球上有：
133,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000 個原子。此數字為 51 位數十進制。Starknet 的 field element 是 modulo 一個大質數 P (2**251 + 17 * 2**192 + 1)，其為 76 位數十進制。所以我們可以開一個合約，每一個 felt 質對應到一個原子，可以 account for all atoms on earth，並且可以重複 10**(76-51) = 10**25 次；人類粗估宇宙總計有一萬萬億顆星球，即 1*10**20。因此 Starkne 的 felt domain 可以映射成一個完整宇宙裏每顆星球的所有原子，相互 non-fungible! -- 延伸思考：可以做到絕對質量守恆，即原子總數不變並且原子之間 non-fungible (用 erc1155 做，token 之間 non-fungible，而 token type 為元素種類)]

Alternatively, we could define the matter operator as a probability of observing an atom at a given set of spatial coordinates at a specified time. With either continuous space or discrete space possesing a fine grain relative to the atoms, this is required to preserve the concept of unitary atoms as our fundamental building block of matter.

Let us now add a constraint that our simulation should allow the construction of universal computers. To do this, we can add rules that govern how neighboring atoms of various types interact to transform information. ... This information cannot be stored in the set of interactions; it must be stored somehow in the matter. ... the set of interactions, and the information they contain, is fixed upon creation. This assumes, of course, that our physics is in fact not time-varying ...

With a sufficient set of interactions (yet to be defined) and at least two bits of effective information per atom (note: one is its flavor, the other is the information it carries), we can construct a universe that contains reusable computers.

(on evaluating the universe state) ... we could say we will start everywhere simultaneously and achieve convergence across the entire universe within each ‘frame’ given a discrete, implicit model of time. ... The issue with the first solution is that it requires solving the entire universe jointly on every timestep, which is expensive. It is desirable to choose a solution that allows us to lazily evaluate our universe only as the information is needed. This idea of “as the information is needed” demands a concept of an observer: broadly, something to require the information. An observer is something that takes a measurement. This also means that if there is no source of external randomness available, the simulation is entirely deterministic. ... Using quantum computers, where the memory is composed of qubits and unobservable (nonteleportable), avoids this constraint. We go back to the question of laziness. If the computer running the simulation is classical, it can only perform what we can call “Type I” laziness: instead of storing an explicit representation of the state of the universe, it can store generating functions which produce that state. These generating functions can be called asynchronously, but they compress space in exchange for time; the “framerate” of the simulation will be determined by the slowest measurement operation, which limits how lazy you can be. If the computer is quantum, it can implement “Type II” laziness, in which the information representing the universe can be compressed (e.g., entangled) with no cost in time.

As a sequence of floating point operations progresses, the accumulated error is generally chaotic.[3] The error never decreases, though it can stay constant through some operations that by chance or construction can be done exactly. We can consider this compounding error as a measure of entropy for our simulation, and it implies the existence of a principle similar in nature to our own second law of thermodynamics. Note that while, to us, the compounding error is interpreted as a progressive loss of information, within the simulation it would merely imply a fundamental limit on measurement or ability to easily predict certain phenomena which become non-smooth, but not overall conservation violations.

**This has been a brief tour of some of the challenges of building an MMO “from scratch” that provides a very high degree of flexibility. Importantly, this analysis provides no guarantees that such a universe would be fun, which is an essential pre-requisite for any successful virtual world. However, the hand-design of mechanics in narrowly constructed universes suffer from a universal lack of depth, and this is a critical bottleneck for the realization of an compelling long-term alternative to the world most people inhabit today.**

[想法：把"autonomous agent" 和 "generative universe" 兩件事結合：autonomous agent 是 observer，四處游走探索，獲取觀察數據並推導宇宙法則，法則為極龐大的數學結構 -- depth of the universe。]
