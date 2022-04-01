# Pre-work - *Memory Game*

**Memory Game** is a Light & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: Jacob Segal

Time spent: 9 hours

Link to project: (https://glitch.com/edit/#!/tremendous-petalite-silk)

## Required Functionality

The following **required** functionality is complete:

* [✔] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
* [✔] "Start" button toggles between "Start" and "Stop" when clicked. 
* [✔] Game buttons each light up and play a sound when clicked. 
* [✔] Computer plays back sequence of clues including sound and visual cue for each button
* [✔] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess. 
* [✔] User wins the game after guessing a complete pattern
* [✔] User loses the game after an incorrect guess

The following **optional** features are implemented:

* [✔] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
* [✔] Buttons use a pitch (frequency) other than the ones in the tutorial
* [✔] More than 4 functional game buttons
* [✔] Playback speeds up on each turn
* [✔] Computer picks a different pattern each time the game is played
* [✔] Player only loses after 3 mistakes (instead of on the first mistake)
* [✔] Game button appearance change goes beyond color (e.g. add an image)
* [ ] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [ ] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [✔] User has a limited amount of time for each game
- [✔] Centered HTML Elements
- [✔] Time gets updated on screen
- [✔] Player Mistakes get updated on screen

## Video Walkthrough (GIF)

If you recorded multiple GIFs for all the implemented features, you can add them here:
![](https://media.giphy.com/media/zKA41NFlSM9SByLeS5/giphy.gif)
![](https://media.giphy.com/media/xU5Xrrq3I7g1B4n1ea/giphy.gif)
![](https://media.giphy.com/media/oD80g5v3qkjnBJwonV/giphy.gif)
![](gif4-link-here)

## Reflection Questions
1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here. 

[
https://www.geeksforgeeks.org/javascript-cleartimeout-clearinterval-method/
https://stackoverflow.com/questions/10485385/how-do-i-correctly-use-setinterval-and-clearinterval-to-switch-between-two-diffe
https://www.w3schools.com/js/js_htmldom_html.asp
https://www.w3schools.com/cssref/css3_pr_align-items.asp
]

2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words) 

[
The most difficult challenge I encountered was creating a timer that stops the game once the 2 minute time limit runs out. Creating a countdown was straightforward after reading through and understanding the geeks for geeks tutorial on the clearInterval method. However, ending the game once the timer ran out and having the ability to start a new game either after winning or losing before the timer runs out was tricky. To overcome this I divided the problem into 4 steps: create a function updateTimer() that updates the time, inside updateTimer() create a timer that infinitely counts down, use the clearInterval method so the timer stops when time equals zero, find a way to restart the timer after a game ends. By dividing the problem into multiple steps each one building ontop of the previous steps functionality the task became less challenging. The challenge in step two was setting myself up to be able to complete the other steps. Thus, I set a variable called “i” equal to setInterval(function(), delay) which then gave me the ability to complete step three because I was able to clear the interval by using the variable “i”: clearInterval(i). In addition, another challenge I faced was leading into step 4. After first implementing my attempt I found that the timer continues to count downwards after the game ends because time is set to 120 again and there is nothing preventing the setInterval function from running. To solve this issue I set time to be 120 once the game starts and ends. Then I created an if statement in updateTimer() that only allows the interval to continue if the time is less than 120. Thus, by doing this I can call the updateTimer function once per game. The updateTimer then deals with the minimum value of 120 by setting time equal to 119 which allows the time to decrement only after the function is deliberately called again in the startGame function. After solving the continually countdown issue I had the tools necessary to complete the fourth step properly. Thus, I set time equal to 120 after either the user wins or loses and used DOM to change the innerHTML of the timer so that the time is displayed as 120. This essentially resets the functionality and user interface of the game, so the player can continually play the game with the same presets.
]

3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words) 

[
I’m curious about what divides the back-end and the front-end. In the past I have heard from youtube videos and people around me that Javascript is a front-end language. After completing this fun project I would like to know more about Javascript’s use as a backend language and how to incorporate more standard back-end languages into a project like this. For example, would Javascript only be used for DOM manipulation in an industry setting while another language is used for the logic or is JavaScript used in the way we used it, for front-end manipulation and logic, in the industry. Another question I have is how to best structure a program as the size of it increases. How do you keep track of the various JavaScript methods, html blocks, and css styles. While working on the project I thought about creating multiple css files each for addressing different aspects of the project like buttons, html body, interactive components and if it would be appropriate to do so. So as I continue to advance my HTML/CSS/JS knowledge, I desire to learn strategies to best organize code. While adding additional features to the Light and Sound Memory Game I realized proper structuring of code is essential. There are a lot more things I would like to know about web development, but to conclude I wonder how a framework such as ReactJS or Angular can be best used to increase the simplicity of a program like this and if they are even able to at all. 
]

4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words) 

[
Recently, I have gained an interest in pianos, so the frequencies the blank game buttons produced intrigued me and led me to try to figure out a way for the buttons to play a song. Instead of being given a set frequency for each button, what if I could create a frequency map that contains the frequency of each note in a song (for example Twinkle Twinkle Little Star) and had the memory game continue until each frequency was played or the player got 3 strikes. This would be challenging to implement since the pattern is randomized at the start of each round. Therefore, I would need a way to assign the next frequency in a song to the next button. One way I was thinking about attempting this was creating a count variable that counted the max number of buttons the current sequence in the pattern has. So for example if it is the 4th round then there would be a count of 4. Then I would access the frequency of the button in playTone() by doing o.frequency.value = freqMap[count]. This is different than before since the argument that freqMap takes is count instead of btn. This would allow the freqMap to be able to access every frequency in the frequency map created for each song. I am not entirely sure if an approach like this would work but if I had a few more hours to think about and attempt to solve this problem I would first approach it like this. Depending on how long it takes me to add this feature, another feature I would add is the ability to choose a song or have the program assign a random song, chosen from a collection of them stored in a two dimensional array.
]



## Interview Recording URL Link

[My 5-minute Interview Recording](your-link-here)


## License

    Copyright [Jacob Segal]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.