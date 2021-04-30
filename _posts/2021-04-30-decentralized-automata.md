---
layout: post
title:  "The Autonomous Dimension "
date:   2021-04-30 00:00:00 -0500
categories: idea
---

Recent blockchain development has generated a few new technological primitives: crypto, DEX, NFT, and DAO.

They are interesting for many reasons - ideological, intellectual, egalitarian etc. They are particularly interesting to me because they, together with continuing progress in AI research and semiconductor technology, point to the possibility of a new kind of human world, and that is a world where the common human completely disregards money as something worthy of attention, where money serves as the unseen backbone of the world infrastructure.

---

When I review my life in retrospect, I find it a disappointment that, increasingly over time, I have been spending the majority of waking hours in the attempt to make and preserve financial wealth; it does not interest me in itself, yet I am grasped by a perceived need to do it nevertheless, although what fundamentally interests me is to imagine interesting versions of the future and drive the efforts in realizing them. I suspect it is the same for the majority of humanity in the civilized society. I further suspect that for the majority of humanity, the act of making and preserving financial wealth (through creating goods and services of value to someone else) in itself is not desirable; it is desirable only because it leads to financial wealth accumulation whether deterministically in case of employment contract or probabilistically in case of investment. The interestingness of the process is a separate question and happens by coincidence. But why accumulate financial wealth?

I know that financial wealth is an abstract concept, thus completely unnatural to human. Yet, admittedly, there is a visceral response in me when any nontrivial amount of financial wealth is given to me whether by my employer or by the markets. It means that the accumulation of financial wealth as an unnatural concept is connected to more visceral and natural desires, which means there are things I very much want to do that require certain level of financial wealth which I lack; those unfulfilled desires prompt me to chase financial wealth as a intermediary target. But isn't it absurd to spend the majority of waking hours in making money (or recovery from the act of making money through activities such as mind-numbing entertainment)?

I believe we can do better. I believe there is a way to dramatically increase the interestingness of lives of many people by eliminating the need for accumulating financial wealth in our civilization. I am interested in creating such a world where the accumulation of financial wealth is no longer of concern to the common human, a world where abundance is extraordinary.

---

Why does crypto, DEX, NFT, DAO, and AI point to the possibility of a new kind of human world? It shall be more obvious when one views them from a particular angle.

Crypto can be viewed as a fully autonomous infrastructure for financial value denomination believed, trusted, and relied upon by increasing proportion of human population; it incentivizes participation to grow and sustain itself (e.g. profitable mining or staking operation).

DEX can be viewed as fully autonomous market for exchanging crypto; it also incentivizes participation to grow and sustain itself (e.g. Balancer's auto-rebalancing via external arbitrageurs; [I wrote about this last year in Mandarin](https://hchsueh.com/2020/04/balancer-bonding-surface)).

NFT, for now, can be viewed as a pointer on the blockchain for something else of interest, which is somewhat analogous to a pointer in the memory indicating where a particular data or program sequence is located.

DAO, for now, can be viewed as a primitive for collective decision-making by blockchain-based entities.

Finally, AI can be viewed as a very broad field of work with a single holy grail of creating truly autonomous agents usually on silicon substrate and may or may not be physically embodied. AI not only progressively makes intelligent decisions (as in the discriminative models in ML parlance, for which reinforcement learning is a powerful category of algorithms), but also creates interesting and valuable data (as in the generative models in ML parlance, among which GAN is a promising direction).

Combining all of these concepts, it is not far-fetched to conceptualize a version of the future where digital autonomous agents exchange assets via crypto at DEX markets, both create and manipulate data (none-code digital assets), program sequences (code snippets/ AI models), and real world assets (contracts) tied to NFTs, and make decisions collectively via DAO. This "layer" of autonomous agents operating on crypto infrastructures could be handling financial resource allocation as well as the creation and delivery of both digital goods and services and physical goods and services so efficiently and compellingly that the majority of us no longer put thoughts to accumulating financial wealth, the same way the majority of us do not put thoughts to acquiring water, food, electricity, mobility (solved by industrial revolution and aviation advances), appliances (solved by market mechanisms), and information (solved by the web technology). Imagine this: one day we will no longer put thoughts to money. Money becomes a "solved" problem. Granted, something else will be seen as the new dominant scarcity and become the object of pursuit for the majority of human beings, which according to Albert Wenger at USV would be [attention](https://worldaftercapital.org/). Either way, that future shall be the next phase of human civilization and seems extremely interesting.

---

Although the future seems unpredictable, we can passively* make educated guesses based on evidence as well as proactively influence its course. In this section I offer evidence and observations supporting the above version of the future.

\* *We can question if passivity is possible e.g. given the Observer Effect of physics, even only metaphorically.*

1 - AI workload growth and continuing Moore's Law

[Investment into AI chip companies](https://www.eetimes.com/mega-investment-in-ai-chip-startups-is-justified-true-or-false) have been growing hotter for the past decade. There are many catalysts for this (slowdown of Moore's Law and Dennard Scaling, the drive toward hardware specialization, increased demand for AI computation efficiency driven by massive recommendation engines built by social network companies etc) One recent example is Sambanova which raised its Series D round which values it at the $5B level.

Another promising thread is the growing evidence of the potential for photonics to not only resuscitate but turbo-charge Moore's Law. Lightmatter's upcoming product applies photonics, which is superior in linear math computation, in accelerating the linear math portion of AI workload, and is estimated to be able to speed up AI computation by 10x at 1/10 of the power (i.e. 100x energy efficiency) when compared to current state of the art e.g. Nvidia's A100 (the performance boost could be even greater if going wavelength-division multiplexing; see this [recent Forbes coverage of Lightmatter](https://www.forbes.com/sites/johnkoetsier/2021/04/07/photonic-supercomputer-for-ai-10x-faster-90-less-energy-plus-runway-for-100x-speed-boost)) Photonic interconnect further accelerates inter-chip communication while saving power, enabling the deployment of ever massive and complex AI models. (disclosure: at the time of writing, I am a digital design engineer at Lightmatter.)

The booming of the entire tech industry of the past many decades has been fundamentally powered by Moore's Law in a certain sense; if the continuation of Moore's Law relies on the prioritization and specialization of AI workload, the entire tech industry will follow suit i.e. where there is higher computational capacity, applications will follow (an analogy is the hugely surplus in network bandwidth built from capital raised during the Dotcom Bubble later enabled numerous applications such as social networks). Recall how the availability of GPUs catapulted deep learning in ILSVRC 2012 (AlexNet). With photonics boosting AI capacity by 100x, a significant proportion of our tech future will be powered by AI. The only question is how.

2 - RPA

The advent of Robotic Process Automation realizes our common imagination of what AI means to the labor force: replacement. Manual tasks are automated by RPA programs. This clearly shows how human-provided services (work that gets paid, therefore priced) can be provided by automation processes i.e. code.

3 - Organic evolution in the NFT space

The original imagination of what NFT enables, from ERC-721 proposal, is the representation of ownership of "physical property, virtual collectibles, and negative-value assets (e.g. loans)." There are two questions that spark heated debate since the beginning: where is the digital  content represented by the NFT, and what does an NFT owner really own if the digital content tied to the NFT is accessible and viewable by the public? The answer to the first one is either on-chain (which takes up storage in the usually-space-constrained blockchain), or on a separate storage solution (such as IPFS). The answer to the second question is the right to the content, but not the content itself. Interestingly, as generative art picks up momentum in many fields (AI research, PCG technology in computer game and animation etc), new projects are created to tie NFT not to the artwork content itself but to the process of generating the artwork content, which being a piece of compact code snippet is fully contained in the NFT itself on-chain. One example is Autoglyph by Larva Labs. This article aggregates other examples in this space (such as Neolastics). Owning the right to the process instead of the right to the outcome is an interesting idea - imagine owning a digital *clone* of Vincent van Gogh instead of owning one of his artworks; you can ask *your* van Gogh-clone to create more artworks. In other words, what is owned is dynamic and alive, which is in sharp contrast to the static files represented by NFTs now. It is the expansion into the time dimension from static screenshots.

Another organic development in the space is recently announced by AlphaWallet team: [AlchemyNFT](https://medium.com/alphawallet/alchemynft-rise-of-synthetic-nfts-320ee5fe1e04), which allows the creation and manipulation of synthetic NFTs. All evidence points to how much of NFT's potential lies unexplored beyond speculating over prices of trading cards.

4 - AI and game; the race to building the metaverse(s)

To enable truly emergent content and spontaneous experience, AI must become an integrated part of our future video games, or as many put it when games scale out to engulf daily lives of people, the metaverses. A16Z has published an article [Meet Me in Metaverse](https://a16z.com/2020/12/07/social-strikes-back-metaverse/) that nicely sketched out the rationale and traced recent progress in this direction.

In fact, the tech giants have dabbled in this direction, albeit unsuccessfully. Google Stadia has created internal game studios in the attempt to create ML-powered games. The most visible example is their Project Chimera ([MCV/Develop](https://issuu.com/bizmediauk/docs/mcv-develop_956_april_2020) has a nice interview of Stadia's efforts in ML game development in April 2020; see p.34-38). Amazon also jumped in, with Jeff Bezos personally instructing to "make games with ridiculous computation." Neither Google or Amazon has published a game successfully in this direction to date; Stadia shut down its internal studios recently, while Amazon announced a series of bad news in its game development effort. Facebook's RivalPeak is a very interesting experiment in AI-enabled entertainment program, showing signs of early traction. It could be said that with complex corporate politics and procedures to follow, big corporations however powerful they are will not be the ones making headway here, because creating ML-powered games will be a great paradigm shift away from existing game development process, requiring many nimble trials and errors into the unknowns.

In the startup world, the LA and Beijing-based [RCT Studio](https://rct-studio.com/) is making promising progress by incorporating reinforcement learning in the game runtime. [Agence](https://www.agence.ai/), a tight collaboration between filmmakers, artists, and  machine learning experts at Google, produced a "dynamic film" that leveraged reinforcement learning to enable three-way co-creation of game narrative by the film creator, audience, and AI.

From big game developers' perspective, the recently-IPOed Roblox has dedicated [R&D efforts](https://blog.roblox.com/2020/05/scaled-bert-serve-1-billion-daily-requests-cpus/) into deploying huge machine learning models. Gabe Newell, the cofounder of Valve and the creator of Steam, pointed to the possibility of [single player games powered by AI completely eclipsing multiplayer games in nine years](https://www.spieltimes.com/news/gabe-newell-on-the-future-of-single-player-games-in-game-characters-to-be-as-smart-as-humans-in-nine-years/) (2030).

Thinking from the first principle perspective, when virtual and dynamic world engulfs our daily lives, the goods and services (experiences) provided in those worlds must rely on concrete economic infrastructure. My opinion is simply: as AI becomes the primary producer of digital assets (3D models, skins, sound effects, personality configurations etc), what needs to be tokenized is not just the digital assets, but the AI themselves, either in the form of code or the statistical model parameters.

5 - The emergence of data economy to facilitate AI training

Trent McConaghy at [Ocean Protocol](https://oceanprotocol.com/) has pointed out [this direction](https://blog.oceanprotocol.com/nature-2-0-27bdf8238071) in 2018 and is dedicated to building the data economy. Ocean Protocol's mission is to build marketplaces for data-asset publication, discovery, and consumption and for enabling [privacy-preserving AI training](https://blog.oceanprotocol.com/how-ocean-compute-to-data-relates-to-other-privacy-preserving-technology-b4e1c330483).

6 - The possibility of personal data explosion: BCI

[I wrote about Elon Musk's NeuralLink from the man-machine symbiosis perspective last year](https://hchsueh.com/2020/05/walkthrough-neuralink). With the increasing maturity and eventual human adoption of BCI (brain computer interface), there will be significantly higher bandwidth of brain data upload from each individual, bringing everyone's daily mental activities, preferences and tastes closer to AI's reach. How do we treat these realtime and fine-grained personal data? We have to tokenize them for ownership (imagine if big tech companies own your thoughts; you would obviously demand ownership of your thoughts and their derivatives), and privacy is of upmost concern here. However, current NFT standards does support owning the content, which could be utterly incompatible with brain data tokenization. One way is through privacy-preserving compression such as synthetic data generation (matching probability density functions via training statistical models), which means we will not be tokenizing the collected brain data itself but tokenizing the AI that is trained on those brain data.

---

In this section I sketched out a rough course of action towards creating the aforementioned version of the future.

Starting from long-term vision, we will have to build what I refer to as decentralized automata, or DA (with respect to decentralized autonomous organization which will be owned by DAs). DA exists on blockchains where access to code execution is restricted to the owner of its pointer. DAs can trade codes as assets, and reassemble its codebase. So we also need to build a software/AI model architecture that is securely composable, decomposable, and mutable.

Short-term R&D is to build the token standard and economic mechanism for code/AI model ownership (not only the ownership of right, but the exclusive ownership of using the code/AI model) as well as its composition / decomposition / mutation. Think synthetic NFT but for AI code. One simple conceptual solution is to store code in fragments such as in Filecoin's fashion, whose locations are reshuffled every time the pointer changes hand.

Mid-term R&D is to build the software and blockchain standards for DA. We will facilitate the realization of the following:
- Source control (e.g. Git) is for DA to manage code versioning and merge code;
- DA will carry out code review process (rule-based / simulation-based);
- Code, models, and parameters are traded on the blockchain by DAs for their own enhancement with respect to metrics defined by themselves.

Long-term R&D is to bootstrap DAs & associated DA-owned DAOs as a whole autonomous economy, which I refer to as the autonomous dimension.

In this version of the future, the autonomous dimension will curate state-of-the-art problems into interactive challenges for individual human, who by overcoming those challenges earn rewards; the reward may very well be non-financial (with universal basic income also implemented by DAs that take over the industry at massive scale). In this way, mundane work will all be handled by machines; the majority of human’s attention is focused at the bleeding frontier of the civilization’s capabilities (civilization = human + machine). To put it simply, what is solved will be handled at scale by machines; human only works on that which is unsolved. No repeat work; reward beyond the universal basic income is only given to those that push the frontier of the civilization’s capabilities.
