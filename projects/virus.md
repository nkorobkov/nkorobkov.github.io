---
layout: project
project-name: Virus War Game
github: https://github.com/nkorobkov/virus-war
date: Ongoing since oct 2019
---

### Idea

The Virus War is a complete information strategic game between two players (similar to Chess and Go) that can be played on checked paper. 

This project is work in progress to:

- Implement the game engine <i class="fa fa-fw fa-check"></i>
- Create an AI that is interesting to play with <i class="fa fa-fw fa-check"></i>
- Optimize the Engine and AI to make moves in less than 10 sec. <i class="fa fa-fw fa-check"></i>
- Create a Web UI to play with AI (work in progress)

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

