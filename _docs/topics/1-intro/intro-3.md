---
title: GE Simplified
permalink: /docs/intro-3/
---

From [https://www.studytonight.com/3d-game-engineering-with-unity/game-engine](https://www.studytonight.com/3d-game-engineering-with-unity/game-engine)  

## Components of Game Engine

A Game Engine is created to develop games, just like any other IDE for any particular language programming. All the components in the game engine are built and integrated to support the motive of game development.  

### Input

A game is nothing if it cannot be played, the game engine provides with support of array of input devices like mouse, gamepad, touch etc while also providing support for devices like gamepad, joysticks etc. There are many different ways of handling an input, two most commonly used are through: events and polling. Input events are captured by the computer (like right click of mouse, or pressing arrow up key etc) and your custom code is triggered based on what input was received. Polling is used to get the position values, for example on which coordinates(x,y) does the mouse pointer is, or tilt angle of Game stick or the Smartphone using which you are playing the game.  

### Graphics

Graphics in a game decides its fate. 3D graphics are designed using 3D assets, which are developed and designed in external 3D rendering programs like Maya, Blender etc and are then imported into the game engine. Hence a good game engine must support multiple import formats.  

Game engine provides a lot of features like lighting effects, shadow, bump maps, blending animation etc to make the imported asset look real.  

### Physics

There is a sub-component of the game engine, which is known as Physics Engine. Physics engines are software which allows performing fairly accurate simulation of most of the real-life physical systems like the movement of rigid body (we will perform that practically in later chapter using Unity 3D), soft body mass and velocity alteration and fluid dynamics, bounciness etc. These are complex engines integrated in the latest game engines, are mainly used in video games (usually as a middleware), where the real-time and real-life simulation must be portrayed. Gravity, collision detection, rotation & revolution, speed of objects and other such applications are handled by the physics engine within the game.  

### Artificial Intelligence

Now-a-days, Artificial Intelligence is playing a significant role within the game development. Knowing the kind of weapons the player will be using based on the situation or the behavior of the player gets recorded and actions are performed accordingly, can be done using specialized software embedded into the games. The implementation of AI in games is usually done using readymade scripts that are designed and written by software engineers who are specialized in AI. For example: How our character reacts on hitting a wall, or seeing an animal etc can be done easily by building a trer of behaviour nodes, rather than writing complex code.  

### Sound

Audio and Rendering Engines are a sub-part of the Game engine which are used to control the sound effects and generate 3D animated graphics in your 2D screen. They provide a software abstraction of GPU using the multi-rendering API's like Direct3D or OpenGL for video rendering and API's such as Open-AL, SDL audio, X-Audio 2, Web Audio for audio.  

### Networking

Since a decade now, games support online multiplayer and social gaming, which connects your gaming adventures with your friends. Most of the gaming engines, provide complete support and scripts for such requirements, so you do not have to worry about TCP/UDP traffic, social API integrations etc.  

