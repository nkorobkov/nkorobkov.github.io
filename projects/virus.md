---
layout: project
project-name: Virus War Game
title: Virus War Game
permalink: /projects/virus
github: https://github.com/nkorobkov/virus-game
website: https://viruswar.nkorobkov.com
date: Oct 2019 - Dec 2019

slideshow:
  - url: /assets/virus/1.png
  - url: /assets/virus/2.png
  - url: /assets/virus/3.png
  - url: /assets/virus/4.png
  - url: /assets/virus/5.png

---

### Idea

The Virus War is a complete information strategic game between two players (similar to Chess and Go) that can be played on checked paper. 

This project includes:

- The game engine to process moves and emulate the environment.
- AI that produces logical moves, and beats newbie player. (using minimax)
- More sophisticated neural-net AI that does not quite reach level-3 minimax performance.
- Optimizations for the Engine and AI to make moves in less than 10 sec. 
- Web server to host AI API.
- Web UI to explore the game and play with AI. *[frontend code](https://github.com/nkorobkov/virus-frontend)*
- Session Controller to hold sessions and allow users to create rooms and play with each other online.

### UI

{% include slideshow.html %}

### Rules of the game

1. The game is played between two players on an empty 8x8 board. One player plays with **Blue** viruses and the other with **Red**.
2. **Blue** makes the first move, after which **Red** and **Blue** alternate.
3. Each move consists of three separate consecutive moves. We will call them "steps".
4. A step can only be made on an accessible cell that is empty or contains enemies virus. 
    - Step on empty cell called "reproduction" and produces a new virus.
    - Step on enemy virus called "killing" and it replaces enemies virus with "base" of your color.  
5. Bases could be in two states: active and inactive.
    - A base is considered to be active if it is in contact (vertically, horizontally or diagonally) with another active base or virus of your color. 
6. You can only make steps at cells that are in contact with your active bases or viruses. 
7. You lose the game if you have no valid moves. 

*you can see the same rules in more detail on the project site itself <viruswar.nkorobkov.com>*

