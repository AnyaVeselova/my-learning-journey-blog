---
title: 'Snake Game '
description: >-
  This is a project I built for "Founders and Coders" software development
  apprenticeship. One of the requirements was to build it using only HTML, CSS
  and JavaScript. Look further to get to know how I accomplished this goal.
author: Anna Veselova
repoName: snake-game-fc
date: 2023-07-03T16:51:43.559Z
tags:
  - post
image: /assets/blog/screenshot 2023-07-03 175907.png
imageAlt: An image of the "Snake Game" project
---
**How did I build the game?**

**HTML and CSS:**

**Firstly, **I set up an HTML for the game by creating a grid container, that contains the title of the game and mode switching button, the primary grid, where the game takes place, the div with the information about the game, and the container for buttons, which appear on small screens. I styled it with CSS, using grid-area property and a "mobile-first" approach, which means that I styled everything for mobiles first, and after that, I created media queries for bigger screens. For the buttons, I conditionally rendered them on small screens by watching the width of the screen in JavaScript with the use of **window.innerWidth** property.

I styled the snake itself by rounding the snake's divs with border-radius. I set the background image of the snake head to a png file, so my snake can be true to itself, but I **encountered a problem** when I was creating the move() function: the snake's head png didn't rotate in the direction it was moving. I **solved it** by rotating the snake's head in **if/else statement** on the direction change. After that, I made sure that the following squares don't rotate by mapping through the squares and setting the rotation to 0 degrees if they don't contain the "head" class. 

![null](/assets/blog/snake-direction.png)

**The logic of the game (JavaScript):**

I started by appending the width*width number of squares to the game field (game-grid). After that, I drew the snake in the grid by creating a currentSnake array, iterating over it using **forEach method**, and parsing each snake index through into the grid squares array, while applying the "snake" class to each one.  

![null](/assets/blog/draw-snake.png)

Then I created the move() function, which is responsible for the core events in the game. I started with a basic snake's moving logic implementation and then created conditions for when the game should finish. The core moving logic is next:

![null](/assets/blog/snake-move.png)

I removed the last element of the currentSnake array using **pop() **array method, then I removed its styling by parsing the element through into the squares array and using **classList.remove method**, I also removed the styling of the snake's head. After that, I **unshifted() **a new head (which is the first element of the currentSnake array + direction) to the currentSnake array and added the styling back to eat, so our snake png could appear in the new square.

The move() function also invokes hitTheWall and hitIItself functions if at least one of them returns a truthy value and redirects into finishTheGame function in such case. HitTheWall function checks if snake's body contains its head, using **ES6 spread operator** for copying the currentSnake array, **array.shift **method for grabbing the head of the snake from that array and **array.some** method to check if the above condition is true.  

The hitTheWall() function checks if the snake's head hit one of the walls by using calculations with modulus. It returns a boolean value. 

Both functions render different popup text content for a **better user experience.**

**Snake's superpower**

Here you can also see a nested function permeableWalls(newHeadval) with a parameter, which I invoke several times in if/else statement while providing a newly calculated head of the snake when it hits one of the walls. I make the snake's head appear at the opposite wall, creating the ability for the snake to go through walls in level 2.

![null](/assets/blog/go-through-walls.png)

**Detecting direction**

The control() function reassigns the direction variable when one of the arrow keys is pressed down. It receives the e.key argument through the event handler function handleKeyMove(). 

**Making the game mobile-friendly:**

For each key button, I added two event listeners: "mousedown" and "touchstart". I used the handleButtonKeyMove function to handle these events. As id attributes match the corresponding event key strings of the arrow keys on a keyboard, I passed the id string to the control() function to handle the direction change.

**Generating the apple:**

In the generateApple function\*\* \*\*I generated an apple by creating a random index and parsing it through into squares array with a further addition of the "apple" class to it. Do/while loop allowed me to avoid the appearance of the apple either on the snake itself or on the walls in the level 2. 

**Eating the apple:**

The way the snake eats the apple is following:

![null](/assets/blog/snake-eats-apple.png)

I detected if the head of the snake match with the apple position, removed the class of "apple", added the tail back to the squares array, modified the currentSnake array so our tail can actually follow the snake and invoked the generateApple function to produce the next apple. 

Along the way, I modified the score and the targetScore of the game, by incrementing the score and decrementing the targetScore. I displayed the scores on every change on the page by using** backticks and curly brackets. **

I also speeded up the snake on every apple bite by creating 2 new variables  intervalTime  and speed, and providing the multiplied intervalTime to a setInterval function every time the snake eats the apple. 

**Level 2:**

I created the levelTwo() function that sets a new targetScore and starts a new game with new obstacles in it. The obstacles (walls) was created by simply mapping through squares array and parsing the numbers of walls arrays through into squares array and adding a classlist of "wall" to them. 

**Saving the best result to Local storage:**

You can see the best score displayed in one of the boxes on the page. That was achieved by saving the best score to the local storage and clearing it on different occasions, so the best score could be displayed when the snake hit the wall and the game wasn't finished, when the level targetScore was achieved, and in the level 2. I made it so the best score could display information that corresponds with each level by clearing the local storage in the startGame() function and when the 2nd level is finished. I also reset the score in the local storage when the snake hits one of the walls or hit itself.

**Starting and finishing the game:**

The startGame() function is responsible for reassigning variables and setting them to their initial state. It also renders the walls depending of weather the level2 variable value. It also returns the snake to its initials state and generates the apple. 

FinishTheGame() function renders the results of the game and if the gameOver variable is true, it renders the message that tells the user that the game is over. It reassigns the level variables and attaches the new event listener to the field of the game, so the game can start again from the first level on its click. 

**Some styling decisions: **

By clicking the moon icon you have the opportunity to play the game on a different theme. I achieved it by toggling the "light" class on :root custom properties.
