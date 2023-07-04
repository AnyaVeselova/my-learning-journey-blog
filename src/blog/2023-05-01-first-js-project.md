---
title: First JS project
description: >-
  This was a project I made following up Scrimba "Front-end career path". The
  topics covered by the project are script tags, variables, numbers, strings,
  console.log, functions, the DOM, getElementById, innerText, textContent. Go to
  the article to find out how I enhanced the course project.
author: Anna Veselova
repoName: people-counter-pj
date: 2023-05-01T22:26:50.655Z
tags:
  - post
image: /assets/blog/counter.png
imageAlt: The image of the project
---
What I learned:

\- a script tag and how to write js code internally and point it to an external js document

\- what are variables (mainly let) and how to reassign them

\- numbers data type and how to work with them (increment, decrement, multiply, divide, set them back to an initial state)

\- strings data type. 

\- console.log() function 

\- how to create a function and how to invoke it in an HTML file. (onclick event)

\- DOM concept (how to use JS to change a website). 

\- I interacted with DOM via document object, using .getElementById() method with an argument inside it, that is equal to the id name in the HTML document.

\- How to set text of an element with innerText and textContent

How it was:

![null](/assets/blog/counterwas.png)

A teacher as usual has done a great job, leaving us room for improvement.

Going above and beyond:

1. I changed the background image and made it responsive.
2. I created a container for the meat of the project and set a max width.
3. I styled the container and its border with the linear-gradient function.
4. I created a flex container for buttons so they can be responsive on the smaller screens.
5. I styled buttons on hover and created an inset box shadow on their active state.

Hints:

1. This is a great way of styling buttons in an active state. It makes them look like they are clicked.

![null](/assets/blog/box-shadow.png)

2. To increment a number and reassign it to the incremented one, we can use a shortcut (ex. count += 1 is the same as count = count + 1)
3. Strings win over numbers if we are to concatenate them. 
4. The innerText property returns:

Just the text content of the element and all its children, without CSS hidden text spacing and tags, except <script> and <style> elements.

The textContent property returns:

The text content of the element and all descendants, with spacing and CSS hidden text, but without tags.
