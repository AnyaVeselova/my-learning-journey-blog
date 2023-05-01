---
title: Meme picker
description: >-
  This project was created at the "The Frontend Developer Career Patch" course
  on Scrimba. I followed the module's lessons and accomplished some stretch
  goals. . 
author: Anna Veselova
date: 2023-05-01T16:36:13.536Z
tags:
  - post
image: /assets/blog/meme-picker.png
imageAlt: A snippet of the project
---
_**What I learned following through the module:**_

![a snippet of the code](/assets/blog/meme-recap.png)

**_Going above and beyond_**

**_1. Click outside the module to close the module_**

This was achieved with the following piece of code:

![](/assets/blog/meme-code.png)

For that, I learned a new powerful element searching method - closest(). The closest() method of the Element interface traverses the element and its parents (heading toward the document root) until it finds a node that matches the specified CSS selector.

The above code allows us to close a modal by clicking anywhere except the modal itself and the "get" button. I needed to exclude the button so that the modal could be opened with its click.



_**2. Displaying more than one gif (in a gallery)**_

For anyone who wants to see all the funny GIFs, I included such an option. I added a new input with a label, which allows us to grab the unfiltered GIFs array and display each of its "cat" objects in a grid gallery. 

By using querySelector I checked if this option was chosen. If it was, I iterated over the cats array with a "for of" loop and then created an HTML string with the data of each object in the array, and finally, I added it to the DOM. 

![](/assets/blog/meme-code-2.png)

I also created the grid class with the grid itself, which I added to the modal. Two different classes for the module in different states (when one or multiple GIFs are displayed) allowed me to iterate between 2 styles.



**_3. Scrollable popup_**

I made the popup grid gallery scrollable by assigning a "scroll" value to the overflow property. By targetting a pseudo-element  ::webkit-scrollbar I managed to make it disappear by using the next code:

![](/assets/blog/meme-code-3.png)

I also found out that ::-webkit-scrollbar is only available in Blink- and WebKit-based browsers (e.g., Chrome, Edge, Opera, Safari, all browsers on iOS, and others). A standardized method of styling scrollbars is available with scrollbar-color and scrollbar-width.
