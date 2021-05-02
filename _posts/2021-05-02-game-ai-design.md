---
layout: post
title:  "Thoughts on Game AI Design"
date:   2021-05-02 00:00:00 -0500
categories: game
published: false
---

Possibilities:
1. Formalize interestingness into a cost function.
2. Acquire or construct a interestingness signal during training and use RL.

Perhaps interestingness can be rephrased as "capturing and sustaining attention." How to formalize attention then? With BCI, this could become infinitely more viable; before the popularization of BCI, can we still make tangible progress? Or, can we work with professional gamers and BCI company to train games based on brain data collected from those gamers?

In [The AI of Halo 1 Combat Evolved | Design & Implementation](https://www.youtube.com/watch?v=kda7rz5qFtI) at GDC 2002, the designer of the game described how the illusion of NPC intelligence is achieved.

The expectations from modern gamers: novel situation, total interactivity with NPCs, significant challenge.

Combat behavior is an area where code and design intersects. Design deals with 3-minute scope (high-level action that requires long term coherency) such as racial personalities and strategies; code deals with 30-second scope (low-level action) such as intelligent decision-making and instant reactions.

The design goals for the AI consist of three parts: intelligible, interactive, and unpredictable:
- intelligible (understandable by player): intent and thought process is transparent to player
- interactive: communication of intent, such as appearing to be impressed, fooled, or thwarted via NPC body language, speech, behavior.
- unpredictable: emergent behavior; instead of randomness, unpredictability means *not repetitive* and is achieved by analog reactiveness to analog conditions as well as encouraging player to behave unpredictably, triggering unpredictable situations.

Playtests revealed things to avoid: subtlety, looking broken/dumb, insufficient challenge.

Potential path: human designer designs the "model for interestingness"; AI train on stimuli from this model as well as stimuli collected from gamers. In fact, there may be more parties involved: human gamers, NPC-driving AI, game-world-creation AI, and designer-crafted interestingness model.
