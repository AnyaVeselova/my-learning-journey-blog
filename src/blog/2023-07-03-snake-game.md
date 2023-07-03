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

![](/assets/blog/snake-move.png)

I removed the last element of the currentSnake array using **pop() **array method, then I removed its styling by parsing the element through into the squares array and using **classList.remove method**, I also removed the styling of the snake's head. After that, I **unshifted() **a new head (which is the first element of the currentSnake array + direction) to the currentSnake array and added the styling back to eat, so our snake png could appear in the new square.
