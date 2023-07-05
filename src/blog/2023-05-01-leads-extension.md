---
title: Leads extension
description: >-
  This is the project I built and enhanced while following Scrimba course. Look
  inside and you won't recognise the initial project.
author: Anna Veselova
repoName: 'chrome-leads-extension '
date: 2023-05-01T22:17:35.828Z
tags:
  - post
image: /assets/blog/my-extension.png
imageAlt: The image of the project
---
What I learned on the Scrimba "Making websites interactive" module:

![null](/assets/blog/extension-recap.png)

**Important takeaways:**

If possible, use const. If not, use let.

DOM manipulation comes with a cost, so changing innerHTML outside for loop is better.

You clear out the input field with inputEl.value = ""

Function parameters are located inside of the function while arguments are outside.

**Scrimba's final extension:**

![null](/assets/blog/scrimba-ext.png)

**My final extension: **

![null](/assets/blog/my-extension.png)

**Going above and beyond:**

1. While the Scrimba project only allows us to create a list of links by grabbing them from the current tub or manually typing it, it hasn't got the option of manipulating each list item. 

I added this opportunity by creating 2 buttons near each list item in the render function, so we can delete or copy the one we need. 

2. I learned a method of creating a unique id and gave it to each button.
3. I then created a function for our buttons where I iterated over the list of links and found the button by its id by comparing it with the id of the event target.
4. I made the delete button to be able to delete its previousElementSibling (our link or lead) by splicing it from the leads array and then renewing the array in localStorage.
5. The same was done with the copy button, only the functionality of it was to copy the specific lead to the clipboard. I changed the image of the copy button on click so the user can know that the link was copied. 
6. I customized the design of the extension by making buttons round and by adding box-shadow to them. By eliminating box-shadow when buttons are in an active state and by playing with the transform property the "clicked" effect is achieved. 
7. I made buttons interactive by adding different styles on hover, focus, and active states. I changed the outline of an input field and changed its border on focus. It's achieved by targetting the input field like that: input\[type=text]:focus {border: 3px solid #5f9341;}
