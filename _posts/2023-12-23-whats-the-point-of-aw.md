---
layout: post
title:  "What's the point of Autonomous World?"
date:   2023-12-23 00:00:00 -0500
categories: idea
published: true
---

Special thanks to Paul Hsia for inspiration.

Autonomous World has established itself as one of the interesting narratives in the blockchain space. As a narrative, it centers around an aesthetic that appeals to critics of various artistic mediums and a group of playful technologists. It is buzzing with multidisciplinary energy. To date, I believe the community behind the narrative has roughly agreed that the ultimate goal of autonomous world is to enable "multiplayer storytelling in permissionlessly expandable and moddable Warcraft-like virtual world built on a credibly neutral computing substrate". Some practitioners of this narrative promote a simplified version of the vision: to run World of Warcraft on a credibly neutral computational substrate, preferrably in Greater Ethereum City. Perhaps we can call this world the Autonomous World of Warcraft, or AWoW. The appeal for building AWoW is that no attribute of any item or character is subject to changes by a single powerful entity such as the game operator company, and that any developer can fork, extend, and mod the whole or parts of the AWoW codebase permissionlessly. This dream is exciting in its own right, but it's not my dream.

This essay documents my thoughts on *What is the point of Autonomous World?*, a presentation I gave at Now Here Book Store on Dec. 14.

<img src="/assets/wtpofaw-1.jpg"/>

### An end-to-end reconsideration of the metaverse problem à la Matthew Ball
To me, one of the exciting engineering problems of this century is to solve the "Metaverse problem". The m-word has a bad reputation from being abused, so this "Metaverse problem" warrants a clean definition. The Metaverse is defined by Matthew Ball as:

> A massively scaled and interoperable network of real-time rendered 3D virtual worlds that can be experienced synchronously and persistently by an effectively unlimited number of users with an individual sense of presence, and with continuity of data, such as identity, history, entitlements, objects, communications, and payments.

<img src="/assets/wtpofaw-5.jpg"/>

The "Metaverse problem" can be decomposed into three sub problems:

1- **Concurrency infrastructure**. How to build a distributed computing infrastructure to support massively concurrent participations from people and machine processes around the world? On the time frame of the next few decades, the Internet will likely not be replaced as the most suitable communication system on our planet for building the Metaverse, so for now assume this infrastructure will be built on top of the Internet. Two major classes of distributed computing system exist on the Internet: the Web, and the blockchain. The Web features a client-server interaction model for distributing resources over the Internet. The blockchain features a distributed state machine, whose state is mutated by fully-serialized transactions, whose ordering is determined by some consensus protocol. It remains questionable whether either of them, or the combination of them, is suitable for making the concurrency infrastructure required for running the Metaverse.

<img src="/assets/wtpofaw-6.jpg"/>

<img src="/assets/wtpofaw-7.jpg"/>

2- **Standards, protocols, and their adoption**. For interoperability to happen, meaning that different digital entities interoperate across different digital contexts while preserving a meaningful degree of continuity in their representation and behavior, these entities and contexts have to follow some sort of standards and protocols around data presentation, computation, and communication. This is extremely difficult given the current landscape of video games where both the technical architectures and "business architectures" of games developed by different companies are fairly incompatible. This indicates an *impasse*: it is not the Metaverse if a single company governs and enforces its standards and protocols (similar to John Carmack's statement), but it seems virtually impossible for a roster of for-profit virtual world operating companies around the world to come to an agreement on a common stack of standards and protocols because that usually disrupts the revenue models of these companies. This problem seems isomorphic to the problem that the Internet (called internetwork in an older time) addressed from the 70s to the 90s, that of fragmented telecommunication networks and the desire to connect them all in the most sustainable way possible. For historical reasons, the fragmented telecommunication networks were mostly circuit-switched networks, with hardware investments and revenue models ossifying this configuration. The internetwork initative championed the then-newly invented packet-switched network configuration and pinpointed the importance of keeping the specification of Internet Protocol singular and small ie the hourglass architecture. This allows different transport-layer and application-layer protocols, which are located above the hourglass's waist, to interoperate with different physical transports, which are located below the hourglass's waist. Can an hourglass architecture evolve for self-soveriegn virtual worlds? How would it evolve?

<img src="/assets/wtpofaw-8.jpg"/>
<br/><br/>

3- **The onramp experience**. If the Metaverse were to be bootstrapped, who would onramp first into this new paradigm, tolerating its roughness while helping shape and advance it? It is hard to imagine if pure monetary speculators could play this role alone; in fact the overblown amount of speculation and the failed promises that reflexively incubated it was a big reason why the m-word became tainted. Other than monetary speculators, what demographics would and should onramp first?

To me, the Autonomous World narrative injects a stream of fresh energy into the need to interrogate these hard problems from end to end.

### Simulation as a medium, part 1

<img src="/assets/wtpofaw-10.jpg"/>

One of the interesting goals of building a world computer is to transform our civilizational processes for conversation, collaboration, and decision making. One motivation behind this goal is to help pass the great filter (Robin Hanson) that could be lying ahead, which could critically involve our inability to make binding decisions together to address market failures in the realms of fostering public externality (public goods production) and taming negative externality. One possible approach towards this goal is to popularize computational simulation as a medium for human discourse. Take the issue of global temperature rises as an example. The COP 28 president claims there is no science behind fossil fuel phase-out, and that if fossil fuels are phased out, the world would end up going back into caves. One potential solution to this disagreement on whether certain policy direction has sound scientific basis is to build and evolve the associated scientific simulations in virtual places that welcome public participation and examination. In the present day, I think relatively few would see the Internet as useful in hosting virtual places for communal scientific simulations. On the other hand, we can agree that the Internet today hosts many very popular virtual places for communal entertainment simulations - massively multiplayer online games.

<img src="/assets/wtpofaw-11.jpg"/>

<img src="/assets/wtpofaw-13.jpg"/>

<img src="/assets/wtpofaw-16.jpg"/>

Has the Internet ever served to host scientific simulations for public participation and examination? Yes! One example is that in the early days of the Web, when Java Applet was the dominant technology to run interactive software over the Web, the National Aeronautics and Space Administration (NASA) once ran a Java Applet called J-Track. J-Track draws the live trajectories of more than 100 satellites on a Mercator map of the world, and shades the map to show day vs night in different areas.

<img src="/assets/wtpofaw-17.jpg"/>

This direction is related to decentralised science (DeSci), a form of crowdfunding onchain for scientific research, but different. DeSci focuses on essentially extending the Initial Coin Offering model towards funding scientific research, whereas simulation as a medium focuses on making communal spaces on the world computer for collaborative scientific simulations, advancing scientific discourse, and advocating for science-based policy-making. Circling back to the COP 28 controversy, imagine if there exist autonomous worlds hosting collaborative and traceable climate simulations for experimentation, hypothesis validation, and conversations. These worlds can perhaps be called "scientific townsquares".

### Simulation as a medium, part 2

<img src="/assets/wtpofaw-19.jpg"/>

Constructing virtual worlds from scratch is extremely exciting from the perspective of investigating the ontology of computational worlds, which helps us reflect on the construction of the "atomic" universe we exist in. Kids in early 1970s dreamed of becoming astronauts; kids today aspire to become social media influencers, professional gamers, and Youtubers. If we look pass the debate about which dreams are more worthy, we can see the difference in terms of kids wanting to gain *power over what* - over people or over nature. Astronauts explore the outerspace and as a result help humans gain understanding and access to larger parts of nature. On the other hand, no amount of success from social media influencers, professional gamers, or Youtubers directly contribute to enhancing human's power over nature; instead, these endeavors fundamentally seek wins in adversarial settings against other humans. In other words, these endeavors seek power over people, whether it is about maximizing engagement in the presense of other engagement-maximizing influencers or content creators, or maximizing player-vs-player performance against other gamers. Again, the focus here is not to judge the worthiness of pursuits, but to highlight on the one fundamental difference in their objective and shed light on the drastic difference between the present time and a not-so-older time.

<img src="/assets/wtpofaw-25.jpg"/>

Coming back to simulation as a medium, it prompts the question: how might a computational world with incredible emergent complexity be built? Looking at the table of contents of the autonomous world book published by 0xPARC, a reader will notice many of these topics are essentially investigating the ontology of richly emergent computational worlds. Where does this investigation have to do with gaining power over nature? Because, just like exploring the outerspace and collecting more data might help us understand the universe better, studying and constructing virtual worlds from scratch might help us understand the universe better as well, specifically from the perspective of how we who exist in a higher dimension could create worlds that exist in a lower dimension, and what that tells us about the ways our world, in our dimension, could possibly be created by existence in an even higher dimension than ours.

<img src="/assets/wtpofaw-26.jpg"/>

### Reference

[1] The Metaverse, by Matthew Ball; [link](https://www.matthewball.vc/metaversebook){:target="_blank"}

[2] Watching the Waist of the Protocol Hourglass, by Steve Deering; [link](https://www.iab.org/wp-content/IAB-uploads/2010/11/hourglass-london-ietf.pdf){:target="_blank"}

[3] Internet Experiment Note #2, by Jon Postel; [link](https://www.rfc-editor.org/ien/ien2.txt){:target="_blank"}

[4] Avoiding the Great Filter: Predicting the Timeline for Humanity to Reach Kardashev Type I Civilization, by Jiang et al; [link](https://www.mdpi.com/2075-4434/10/3/68){:target="_blank"}

[5] Cop28 president says there is ‘no science’ behind demands for phase-out of fossil fuels, The Guardian; [link](https://www.theguardian.com/environment/2023/dec/03/back-into-caves-cop28-president-dismisses-phase-out-of-fossil-fuels){:target="_blank"}

[6] Watching the Skies at NASA; [link](https://litux.nl/mirror/java24hours/0672328445/ch03lev1sec4.html){:target="_blank"}

[7] Unlocking Scientific Innovation Through Decentralized Science – Part II, by Christine Strauss; [link](https://law.stanford.edu/2023/07/27/unlocking-scientific-innovation-through-decentralized-science-part-ii){:target="_blank"}

[8] NE Indiana Defense Summit 2023: Discussion with Palmer Luckey (from 36:04); [link](https://youtu.be/pGCOPxje3_c?t=2164){:target="_blank"}

[9] Jailbreaking the Simulation with George Hotz, at SXSW 2019 (from 23:38); [link](https://youtu.be/ESXOAJRdcwQ?t=1418){:target="_blank"}

[10] The Last Question, by Isaac Asimov.
