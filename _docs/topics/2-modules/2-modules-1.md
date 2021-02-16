---
title: Modularisation of Games
permalink: /docs/2-modules-1/
---

We can build games in a modular way. We can separate the physics engine from the rendering process and the rendering process from the AI. There are a number of advantages to this approach. It increases reusability if our game components are not tightly coupled. The skills and knowledge involved in developing the components differ, separating them allows the right people to work on the right tasks. This does come at a cost though, careful management and planning are required to ensure the components of the game link up correctly and the effort is not wasted duplicating work across the modules. Decoupling the components comes at a potential performance cost too, efficiencies can often be made by tightly coupling the components together.  

Game engines are generally built to support this approach. They are designed in a modular, component based way and great effort has been put in to making them as compatible and efficient as possible.  

We've looked (briefly) at the components of a game engine, now we'll take a similar look at games themselves and how we can break them down in to components.

## The Game World

It is often useful to think of what's happening in the game as the *game world* and to distinguish between that and what is displayed on the screen. We call what is displayed on the screen a *game view*. 

The *game world* is everything that exists within the game. Platforms, NPCs, power-ups, characters, walls, guns, bullets, monsters, towns, trees and mountains all "exist" within the game world. (NB we are talking about things which exist/happen within the world of the game, not code constructs).

A *game view* in contrast is the *game world* as seen from a specific time and place.    