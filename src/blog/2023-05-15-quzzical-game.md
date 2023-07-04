---
title: Quzzical game
description: >-
  This is a Solo project I created following Scrimba's "Frontend career path".
  It was a final project in "React Basics" module.
author: Anna Veselova
repoName: quiz-game-solo
date: 2023-05-15T13:17:46.885Z
tags:
  - post
  - featured
image: /assets/blog/quizzical.png
imageAlt: The overview of the project
---

Welcome to the "Quizzical" Solo project!

**_How did I build it?_**

I built it using npm create-react-app on VS Code and local server. The project consists of 4 components (Start, Questions, Footer, and App). All the data props are passed to the components in accordance with the Single Source of Truth principle.

In the App component, the questions and the answers are pulled from the OTDB API, and quiz elements with props are created by mapping through the pulled data.

The Quiz component is responsible for creating, conditionally styling (depending on whether the chosen answer is correct or not), and rendering quiz questions and answers.

The Footer component conditionally renders the score of the game and the button in accordance with finishState and startState of the game.

The Start component renders a welcoming message and a call to action button. By clicking the button the user is redirected to the App component with the quiz itself. I accomplish it by creating a switchScreens function, which flips the toggle boolean state on a button click and conditionally renders the Start component.

**_What did I learn?_**

I learned that React is meant to make my work easier and less repetitive.

I found out the solution how to shuffle the array of answers:

![](/assets/blog/array_shuffle.png)

I practiced creating data-driven pages in React and making components reusable by using props. I mastered the concept of mapping through the data and creating multiple instances of custom components, using props to pass in specific data to each one.

I also learned how to listen to events in React, how to save state, how to conditionally render some elements, and how to handle side effects by using useEffect hook.

_**What will I do differently next time?**_

If I were to start this project over, I would have learned React Router and built it as a single page app.
