---
title: Basketball Scoreboard
description: >-
  This is my solo project that I created relying on Figma design, and using CSS,
  HTML and JavaScript. Go to the article to find out how I managed to create it.
author: Anna Veselova
repoName: basketball-scoreboard
date: 2023-05-01T22:30:48.452Z
tags:
  - post
image: /assets/blog/my-bask.png
imageAlt: The image of the "Basketball scoreboard" project
---
This was my solo project. I created it based on Figma design.

![](/assets/blog/per's bs.png)

**How I accomplished it:**

Firstly, I created a flex container with 3 flex items in it. I used a media query to make it responsive on smaller screens and changed the direction of the flex container. 

Going above and beyond in styling:

I found out about disabled pseudo selector and styled disabled buttons differently (with no-drop cursor you don't want to press such dangerous buttons at all :)

I used font-awesome icons to show the leader of the game and styled it conditionally in JavaScript. 

**JavaScript:**

1. I learned a new .replace() method, which can pick all digit characters out of a string. I used it in order to take a number out of the increase buttons so then we can increase the final score with that number.
2. I took those increase button values out of the DOM with an event.target.innerText.
3. I then converted a value to a number with a Number() method and created a function that increases the score by that value. Every time the value is different, depending on which increase button was clicked.
4. Depending on which section (Guest or Home) the clicked increase button was in, the particular score increases(whether Guest score or Home score). I targeted the sections with event.targer.parentNode.id
5. I learned the addEventListener method, which attaches an event handler to every button, that was clicked, and provided the function from the 2nd paragraph as a second parameter.

**Going above and beyond:**

1. I created a countdown timer and a period element, that increases every 12 minutes by 1. Getting to know the Date object and setInterval method, I faced several issues.

Firstly I created the countdown timer with the setInterval method only, but it couldn't work synchronously with a period. To achieve a more accurate result, I had to use Date.now() method to set minutes, and seconds, and to find the interval between now and the countdown time. 

Within the same function, I created a setInterval for the period, so it can synchronously add 1 point when the countdown timer starts (on the start button click) and continue adding it every 12 minutes.

2. I made the timer start on the click of the start button.
3. I created a reset button.
4. I disabled the increase buttons when the timer is not running and the start button when the timer is active for better UI.
5. I changed the default styling of disabled buttons with a new for me disabled pseudo selector.
6. I learned the "for of loop" to loop through HTML collection of buttons, grabbed with getElementsByClassName method, so I can disable each of them when the timer is not running.
7. I styled font-awesome icons conditionally, using the ternary operator.
