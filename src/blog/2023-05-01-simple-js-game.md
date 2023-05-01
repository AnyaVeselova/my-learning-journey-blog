---
title: Simple JS game
description: dsfsd
author: Anna Veselova
repoName: monstersvshero
date: 2023-05-01T22:38:38.060Z
tags:
  - post
image: /assets/blog/screenshot 2023-03-30 173420.png
imageAlt: hfgh
---
This is a project I built, following the 7th module ("Next-Level Javascript") of the "Front-end career path" course on Scrimba. I added some JS features and restyled the game. 



This module was covering next topics:

![](/assets/blog/module_6-specs.png)

![](/assets/blog/mod_7-specs.png)

Thanks to Tom Chant and his clear explanation, I managed to understand all of the above.



How I built it?



In the beginning, we used a constructor function to create a Character "template" for the game, which then became populated with the data of different characters (this is the way constructor functions work). 



In the constructor function, we used Object.assign method to assign the data from provided objects (as an argument) to this keyword. After that we created a setDiceHtml method, which generated HTML dice string for us with random numbers. Earlier we imported a set of functions from utils.js folder, which were placed there to separate the concerns. One of these functions was created to generate our random dice numbers using an array constructor.



We set the initial state of our dice array (before the attack function is clicked) to empty divs with the help of getDicePlaceholderHtml function. 



We are also creating several core methods, where our character acquires abilities to take damage from the opponent and is given the health bar, that indicates the damage in percentages. The getCharacterHtml method finally creates an HTML string for the character and sets its content to the created methods in a constructor function or to the destructured data from the received character object.

 

All the way through the project we manipulate the data.js file and pass properties of the necessary objects to our methods and functions as arguments.



In index.js file we initialized our individual characters by creating new instances of the Character constructor function. All the functionality of the game is created here. We set the attack() function, which is dealing with setting the dice, taking damage, and deciding whether the character is dead or not. We've got the endGame() function, which is deciding what to render in the finale. The render() function is rendering our characters on the screen. 



One of the coolest things, that we created in the index.js file was the dynamic rendering of monster characters. We used the shift array method to grab and remove the first element in the monster's names array and used it to access the data objects' properties.



At the end of the module, we refactored our constructor function to a class and killed two birds with one stone by learning both syntaxes.



What I added



1. I added real dice to the game. It was achieved by creating an array of dice images and rendering them in the setDiceHtml() method in a Character class. As getDiceRollArray() function returns a random number from 1 to 6, and the images array I provided \[n-1] index when grabbing an image from the array, minding zero-based array indexing.



2. I created a method, that allows the Hero to defend himself by either attacking monsters or restoring his health. 

![](/assets/blog/orc-monster-method.png)

![](/assets/blog/hero-function.png)

As you can see, the Hero can do it only once (to achieve this I use a boolean) when his health is below a limit.



3. I added the "New Game" button, which reloads the page and allows a user to start a new game.



4. And, finally, I changed the background of the body and characters' cards, to make it more appealing to the user.

 

Although it was a small learning project and the changes I made are minor, I believe, that small things matter and they are also enjoyable to learn.
