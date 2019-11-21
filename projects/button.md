---
layout: project

project-name: Jeopardy Button
github: https://github.com/nkorobkov/jeopardy-button
website: https://nkorobkov.github.io/jeopardy-button
date: Jun 2018
permalink: /projects/button
---

### Game

Jeopardy is a well known game popularized on TV. It looks likes this:

<img src="{{site.url}}/assets/button/pic.png" alt="jeopardy" border="1" style="max-height: 450px" />

Rules are easy. The host reads a question and then players try to answer it to gain it's *value* in points. 
If your answer is not correct, you will lose question *value* in points.  
When all questions are done, whoever has the most points wins. 

You basically need 3 things to play it with your friends. They are:

1. Questions to play.
2. Host to read questions and keep scores. 
3. System to determine who was first to come up with the answer.

While the first two things are easily solvable, the third one can be tricky.  
The conventional way of playing Jeopardy at parties includes **clapping** as an indicator of readiness to answer. 
It works reasonably well unless the question is too easy and two players want to answer it almost simultaneously. 

### Button System
 
I propose the solution to this problem that uses computer mice as buttons and online app for answer order management.

#### Hardware
To play with 3 players, get 3 USB mice, plug them into a single host's laptop (Use USB hub, if you run short on USB ports) and hand out mice to players.  
You need to agree with players, that one player would press only one mouse key (left, middle or right) if they want to signal.   
<!---You can optionally modify mice by disassembling them and changing the scheme so that any key would trigger the one signal. 
Or even build the whole system out of single mice, if you  are into electrical engineering.--->
And that's it for the hardware part!

#### Software

To play the game, open the [jeopardy-button](https://nkorobkov.github.io/jeopardy-button/) app in the browser on the host's computer and enter the names of players.   
Press the 'space', and you are ready to play!   

<div class="image_row">
<div class="image_col-3">
<img src="{{site.url}}/assets/button/one.png" border="0" />
</div>
<div class="image_col-3">
<img src="{{site.url}}/assets/button/two.png" border="1" />
</div>
<div class="image_col-3">
<img src="{{site.url}}/assets/button/three.png" border="1" />
</div>
</div>


When a player presses the button, his name would light up in red. If the answer was correct, you can reset the game by pressing 'space' again. 
If the answer was wrong, press 'down' and the other two players would have a chance to answer the same question.  

If no second/third answer would be given within the number of seconds specified in the 'timer' window, the game would be automatically reset, and the question should be discarded. 
You can optionally trigger timer before the first answer to speed up the process.  

#### False Start play mode

There is another play mode, that punishes players for pressing the button before the question is read through the end. Check the 'False Start' field to enable it.  
It this mode you will need to start the timer before the first player can answer. If someone presses the button earlier, they are excluded from the current round.  
The sound would help players identify when the round has started and compete to be the first to answer.  

Press 'backspace' at any time to stop the game mode and gain control over your mouse again. 


### Tech

Jeopardy Button is implemented with **React** framework. It also uses:
- **mousetrap** for keyboard bindings manipulation.
- **gh-pages** for hosting.
- **react-sound** for sounds.










