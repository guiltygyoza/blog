---
layout: post
title:  "Game 2.0 in schematics"
date:   2022-08-06 00:00:00 -0500
categories: game
published: true
---

ELI5: We are moving into the new paradigm of Game 2.0, Autonomous Games, and Onchain Reality.

This essay is a elaborate recount of our presentation at ETHSeoul, Aug 6th 2022.

1- We think the state of video games is akin to web 1.0 - massive skew towards read over write. Gamers embody this persona of consumers passively consuming game content and logic developed by game devs and artists. We call this paradigm game 1.0.

2- When I use Port-a-Fort in Fortnite, I engage with my LMB (left mouse button), aim, and release LMB. The rest *happens* and I simply consume the outcome. I have no access into the program that dictates the geometric transform and structural integrity of the fortress. To throw a Hadouken in Street Fighter, I enter a series of keys under some time constraints. I have no access into studying the associated gameplay animation and hitbox models, let alone changing them. To go into prone in Ghost Recon Breakpoint, I press C. I have no access into the character state machine that describes programmatically the transition of my character from walking to proning. To go into galloping on Roach in Witcher 3, I hold shift and W. I have no finer control over Roach than that, and the point is as a gamer who bought the title on GOG/EGS I cannot implement those finer control mechanics as a gamer even if I know how to. I only buy a spatial-temporal right to enjoy the experience - the games could be discontinued, and the ability to start the game client is restricted to certain geographics.

<img src="/assets/game2-1.png"/>
<br/><br/>

3- A lot of these mechanics focus on quick twitch muscle reactions, or System 1 in the terminology of Thinking Fast and Slow. On the other hand, all 10,000-hour games engage System 2 - slow deliberate strategic thinking. Take AoE2:DE - when performing a Persian Douche, one must engage System 2 to dynamically calculate the optimal population and allocation of villagers working on economy against the requirement of Persian's Town Center construction, while adapting to the outcome of scouting the opponent's setup and while engaging System 1 to micro everything optimally. Yet even with brain-frying activities that engage System 2, gamers are still only consuming the game logic and parameters authored by game developers.

<img src="/assets/game2-3.png"/>
<br/><br/>

4- We are slowly moving towards game 2.0. Humans have the innate desire to express themselves uniquely and be heard - to assert one's existence. When possible, we would prefer actively creating beyond passive consumption. We want to be creat-ive whenever the medium allows. We seek mediums for us to become maximally creative - the right type of programming language, the right kind of working environment, the right kind of artistic mediums, and of course the right kind of games. Let's discuss UGC.

<img src="/assets/game2-4.png"/>
<br/><br/>

5- In-game customization has a long history and can be seen as a predecessor to UGC. Shooting game players love customizing their guns when allowed - the right scope, the right stock, the right barrel, the right magazine, and the right paint. We can call it discrete customization - choosing one's favorite combination of options among a finite and limited range of options.

<img src="/assets/game2-5.png"/>
<br/><br/>

6- A more expressive kind can be called continuous customization. Appearnace editors with more than one hundred slide bars controlling different parts of facial and body appearance give gamers very enjoyable time shaping their characters.

<img src="/assets/game2-6.png"/>
<br/><br/>

7- The most expressive kind of UGC thus far is created via full editors exposed by game devs. Young gamers use Roblox Studio editor to create custom worlds for other young gamers to join and role-play together; these young gamers even learn Lua to script their custom worlds with custom logic. This is UGC at the frontier outside blockchain - gamers learning how to code to play a richer kind of game. Game modding, while giving full expressivity via reprogramming, is not considered here, because we are looking for the pattern where the *canonical* game supports such expressivity, not through modding forks.

<img src="/assets/game2-7.png"/>
<br/><br/>

8- In the blockchain space, Dark Forest pioneered the embracing of gamer-created scripts and plugins, which collectively expands the breadth and complexity of play much beyond what the developer provided. How do we take this a step forward?

<img src="/assets/game2-8.png"/>
<br/><br/>

---

9- I have started to use these schematics as a mental model to reason about building / worlding on-chain. We start with a set of rules spanning a space of play, akin to a vector basis spanning a vector space.

<img src="/assets/game2-9.png"/>

10- Gamers play by exploring the space of play. Developers program and author the set of rules. Developers also operate and/or pay for centralized infrastructures.

<img src="/assets/game2-10.png"/>

11- Because of being closed-source and restricted by licenses, the rules are fully controlled by game developers. Gamers only have indirect influence over the rules via market forces - they can choose to play more / play less, they can upvote / downvote the title on Steam etc.

<img src="/assets/game2-11.png"/>

12- Now what if we move away from centralized infrastructure and embrace blockchain? Specifically, what if we run the computer programs that embody the rules on the world computer? There are multiple implications. Absent private smart contracts using some FHE that is still not practical, the rules become fully open source - in the form of contract bytecode by default that can be disassembled, and ideally accompanied with original source code. This means the rules are fully auditable, which also means any change to the rules can be noticed by anyone in the form of state-changing transactions - inclusive auditability. This also means we can derive various signals directly from the game full on-chain and use those signals to drive value flow, credit attribution, and governance processes.

<img src="/assets/game2-12.png"/>

13- Ideally, we want the gamers who put in the most effort and have the most insights to govern the evolution of the rules. In other words, changes in rules should be *gated* by consensus among the gamers, with their voices weighted by meaningful effort. With rules enforced fully on-chain, it is possible to define and measure meaningful effort quantitatively and transparently on-chain.

<img src="/assets/game2-13.png"/>

14- This gating logic, along with the measure and logic formalizing governance rights allocation, forms a DAO apparently. In other words, we can have fully onchain autonomous rules coupled with fully onchain governance structure, accentuating the A in DAO.

<img src="/assets/game2-14.png"/>

15- Gamers can now directly audit and influence the evolution of rules, embodied in smart contract programs. With games fully embracing content and logic contributed directly from gamers, the division between gamers and developer is blurred. This is somewhat analogous to breaking the fourth wall in theatrical performance. We all become gamers who play, develop, and govern continuously. We call this **rule mutability by merit-based consensus**.

<img src="/assets/game2-15.png"/>

16- Another route of mutability comes from the autonomy of smart contracts. Beneath the mutable rules lie the meta rules that are hardened and immutable. Meta rules are hardened algorithms that govern the autonomous mutation of rules. One interesting example is the mechanics of Darwinian evolution. Think of the set of all species in a world as the set of all playable characters (e.g. Watch Dogs Legion). The Darwinian processes are the meta rules, whereas the lineup of all existing species are the rules (the ontology). New species can come into existence, and other species can go into extinction - all dictated algorithmically and autonomously by the Darwinian processes that are the meta rules. We call this *Autonomous Games*, with **rule mutability by autonomous processes**.

<img src="/assets/game2-16.png"/>
<br/><br/>

17- Blockchain is the most remarkable place to build this new paradigm of games which we call **Game 2.0**: core game systems fully on-chain, which are fully open and immutable by default. They are mutable only by merit-based consensus or by the autonomy of smart contracts. Their space of play are powered, populated, and explored richly by gamer generated content and logic. By incentivizing and being inclusive to flavored and nuanced contributions from each gamer, coupled with nonstop improvement in verifable computation, the content and logic will have such specificity and sophistication that emergent productivity will spawn - productivity back in our physical reality.

<img src="/assets/game2-17.png"/>
<br/><br/>

18- If games are becoming so much more sophisticated and tied to productive activities, are they still games? Are they still fun? We are aligned with Mihaly Csikszentmihalyi in that *Fun is defined as Flow*. Games will give us so much more heightened challenges in different modalities, but precisely because of that, when we meet such challenge with our heightened capabilities, we will have unprecendented fun. This new kind of game will depart so much from video games we have now that the word game will not be able to justify it. We call it **Onchain Reality**.
