---
title: Twitter Clone
description: >-
  A Twitter clone made on "Front-end Career Path" Scrimba course. I set some
  stretch goals and made the project "my own".
author: Anna Veselova
liveBtn: https://twimba-clone-project.netlify.app
repoBtn: https://twimba-clone-project.netlify.app
date: 2023-05-01T16:24:05.655Z
tags:
  - post
image: /assets/blog/twimba.png
imageAlt: A snippet of the "Twimba" project
---

This Twimba project was fun to build because I felt that it's something that real developers can make on their jobs. During the course, we covered the following topics:

![a snippet of the module curriculum](/assets/blog/twimba_studied.png)

_**1. I figured out how to delete a clicked tweet**_

![a snippet of the code](/assets/blog/twimba-delete-tweet.png)

Firstly, I found the clicked object by filtering the array of objects inside the data file. The deleteId is a param that turns into the id of the triggered object when we provide an argument, using the data attribute.

Next, I learned the method of cutting an item from the array if we only have its value. I found the index of the item and then spliced it from the array, using the splice method. This method changes the initial array, unlike the slice method, which makes a new modified copy of the array.

**_2. I made an option for deleting the user's comment and conditionally rendered a trash icon only for this comment_**

![a snippet of the code](/assets/blog/delete_comment-twimba.png)

It wasn't much different from the 1st step, but to accomplish this I filtered the array inside every tweet and used the logical not operator to return all replies except the clicked one.

![a snippet of the code](/assets/blog/conditional_icon-twimba.png)

Then I conditionally rendered the trash icon if the reply handle was equal to the user's value. I used a ternary operator for the goal and curly braces.

**_3. I created the ability to reply to a specific tweet_**

Firstly, I created a form with textarea and input with the type "submit". I set a data attribute to the textarea element and gave both elements id with the tweet.id in it so I can get elements, which belong to a specific tweet.

![a snippet of the code](/assets/blog/comment-tweet.png)

In the code above I filtered the data array with our tweets and returned the "clicked" tweet object. I grabbed input and textarea and then added an event listener to a button. If the textarea element has a value, I added a new reply object to the beginning of the replies array inside the chosen tweet object. After that I rendered the document and cleared the textarea field.

**_4. I managed to save likes, retweets, and comments to local storage_**

I did it by declaring a new variable (newTweetData) that stores tweetsData array and saving it to local storage in a render function. After it's been saved, I fetched it from the local storage in a global scope and reassigned the newTweetData with it.

In this way, local storage tweets objects are continuously being renewed.

If all the tweets were deleted, I reassigned newTweetData back to tweetsData so a user won't be left with an empty app.

_**5. A little bit of styling**_

I borrowed a style of my comments section from this resource:

<https://www.geeksforgeeks.org/how-to-put-a-responsive-clear-button-inside-html-input-text-field/.>

I like how the input button visually appears inside the text field.

![a snippet of the input](/assets/blog/input-tweemba.png)
