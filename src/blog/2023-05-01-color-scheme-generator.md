---
title: Color Scheme Generator
description: SDFSDF
author: Anna Veselova
repoName: color-scheme-gen-solo
date: 2023-05-01T22:49:20.590Z
tags:
   - post
  - featured
image: /assets/blog/color-scheme.png
imageAlt: RGDFG
---

Welcome to the "Color Scheme Generator" Solo project. Solo means I created it without any assistance.

What were the requirements

![](/assets/blog/color-scheme-requirments.png)

What does the project do

This project was built with the help of https://www.thecolorapi.com/docs#schemes API. It sends a specified request to the API, providing the seed color and the mode in the URL endpoint. After that API returns a generated scheme for the provided seed color. The app then renders the received palette.

How I built it

I fetched the needed data from the API in the render() function using the fetch() method and then created an HTML string for the returned color scheme. I iterated over the colors array and created an HTML string for each color and then appended each string to the colorsHTML variable. In the end, I set the HTML content of the colorBlocks element.

I initialized render() function in a global scope and on the submit button click. The first initialization was needed because I wanted the app to render the colors when the page first loading.

Going above and beyond

1. I created the copying to clipboard option when clicking on a color block. I did it with the following code:

![](/assets/blog/clipboard-color-scheme.png)

What it does is it gets the innerText of the clicked color block, which is a hex value, and copies it to the clipboard with the navigator.clipboard.writeText. Besides that, it shows us the popUp of the copied value along with the notification text by playing with its opacity (setting it to "1" on click and back to "0" after 1s using the setTimeout function.

2. I created an option to toggle between light and dark modes on a button click. On the modeBtn click, I toggled the "dark" class, which I tied up to the root pseudo-class selector in CSS. The sun and the moon icons are being toggled by replacing the "fa-moon" and "fa-sun" classes.

3. I made the app responsive by providing a media query, which changes the layout of the app, using grid-template-areas.

What I learned

By doing this project I learned what is HTTP request and understood some of the components which make it up, like:

URLs and endpoints

Methods such as get, post, put, and delete

request body and how to send data to a server

Headers, where we can provide some meta information to a request

Rest APIs

Resources and how restful APIs structured

Parameters, which allow us to specify things in URLs

Queries and how we can filter down the data, which comes from a server
