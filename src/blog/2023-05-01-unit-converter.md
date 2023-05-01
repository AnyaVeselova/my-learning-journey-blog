---
title: Unit Converter
description: sdfdsdf
author: Anna Veselova
repoName: units-conversion-app
date: 2023-05-01T22:24:17.378Z
tags:
  - post
image: /assets/blog/mine_units.png
imageAlt: fgdfgdf
---
This solo project taught me a lot, thanks to the amazing Scrimba course and teachers! 

The requirements were:

![](/assets/blog/requirments_units.png)

... but I decided to make the design of it a little bit better so I can enjoy creating something custom and bring to it a bit of myself.



1. Instead of making a button, I decided to create an input and display the conversion straight away on an input change. Along with this, I learned a new event listener ("input"). The input event fires when the value of an <input>, <select>, or <textarea> element has been changed.



2. To provide a better UI, I made the input autofocused, using the attribute of the same name.



3. In order to meet the third requirement I learned the toFixed() method, which converts a number to a specified number of decimals.



4. I found out how to make a gradient background, using the background-image CSS property. 



5. I faced one problem, which led me to new knowledge. Firstly, I repeated the same code of unit calculation and HTML rendering in the global scope and on input change. I should reassign the value of units because the input value changes and it is one of the multipliers. Instead, I created 2 functions: one is for the maths calculation and the other one is for rendering units in an HTML document. Then I invoked them twice - in the global scope and in the function when the input value changes. Thus I made my code DRYer.



6. I added an option to switch the mode to the "light" one. Firstly I created the toggle switch button, adding some icons with font awesome. Then, using the "change" event listener on an input of checkbox type, I toggled the "dark" class on elements I needed to style differently. In CSS I added the "dark" class to the corresponding elements.



Here's how it looks in the end:

![](/assets/blog/light_units.png)
