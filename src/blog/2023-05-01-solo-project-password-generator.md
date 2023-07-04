---
title: 'Solo project: Password Generator'
description: >-
  This is a solo project created after completing "Essential JS concepts" of the
  Scrimba course. I built it from scratch and went beyond the requirements of
  the project. Find out more about what I learned and how I advanced it.
author: Anna Veselova
repoName: solo-pj-password-generator
date: 2023-05-01T22:20:43.020Z
tags:
  - post
image: /assets/blog/passwordsmine.png
imageAlt: The image of the project
---
**The initial requirements were:**

![null](/assets/blog/initialpasswords.png)

**Going above and beyond:**

1. Instead of a given array of characters I managed to create an array of UTF-16 code units with the help of the String.fromCharCode() method. 

I just iterated over 127 characters in a loop and pushed each character to the array.

Why 127 you'd ask... Because Unicode incorporates the ASCII character set as the first 127 symbols. But what on Earth is the ASCII code? Well, here's the answer:

ASCII is a 7-bit character set containing 128 characters. It contains the numbers from 0-9, the upper and lower case English letters from A to Z, and some special characters. The character sets used in modern computers, in HTML, and on the Internet, are all based on ASCII.)

![null](/assets/blog/codeascii.png)

2. I created an input so the user can set the length of passwords. I created a function, which generates passwords limited by the input value (using for loop) . Inside the for loop, I added random characters to the generetedPassword variable out of the array, created above (using Math object). At the end the function returns the generetedPassword variable.
3. I created 2 toggle switch buttons, each of which determines whether to include certain symbols or not. The first button is responsible for numbers, the second one is for special symbols. Regarding styling them I found the following article very insightful: https://alvarotrigo.com/blog/toggle-switch-css/
4. I created the toggling function, which I then invoked in the passwordGenerate function, so it can generate passwords based on the array we are getting out of conditions that were met in the toggling function.

The function is deciding what will be in the final array, from which passwords will be generated. Using the if else statement the function reassigns the array based on the following states: 

1. Without numbers, but with chars, if chars toggle switch button is ON and numbers toggle switch button is OFF.

I used the filter array method to exclude all numbers from the array. I filtered the array and returned the symbols that meet the outcomes of isNan()

 function.

To check whether toggle switch is "On" or "Off" I used checked property on a DOM input element (it returns boolean).

2. Without chars, but with numbers, if the chars toggle switch button is OFF and the numbers toggle switch button is ONN.

I applied the replace method, turning the initial array toString() and using the regex code, and then turning it to the array with the Array.from(string) method. 

3. Without either numbers or chars if both toggle switch button is OFF.

I did the same thing as in the 2nd statement but with a different regex code.

5. I fixed a bug while creating toggling function. It turned out that the initial array should be reassigned to UTF-16 code units at the beginning of the toggling function, so every time we invoke it we deal with this array, not with the array, already modified by if else statements.

This is the function I described: 

![](/assets/blog/screenshot 2022-12-21 152115.png)

6. I learned how to copy passwords to a clipboard and implemented this knowledge. As an alert, I created a pop-up div that appears for a second when the content is copied (I accomplished it with a setTimeout method). 

Here is the code:

![](/assets/blog/screenshot 2022-12-21 154619.png)

I checked whether the divs with passwords are empty with the childNodes property, then I checked if the clicked element matches the element with "password__container" class, and if these conditions are met, I copied the textContent of the target to a clipboard using : navigator.clipboard.writeText(event.target.textContent)
