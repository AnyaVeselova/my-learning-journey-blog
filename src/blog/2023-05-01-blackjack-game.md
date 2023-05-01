---
title: Blackjack Game
description: dsfdsfs
author: Anna Veselova
repoName: blackjack-card-gm
date: 2023-05-01T22:09:59.796Z
tags:
  - post
image: /assets/blog/blackjackmine.png
imageAlt: dfdgdfg
---
![](/assets/blog/bjrecap.png)

The initial state of the project:

![](/assets/blog/perbg.png)



Going above and beyond:

I decided to bring more life to the card game by displaying real cards. In order to achieve this, I have done the next steps:

![](/assets/blog/blackjackmine.png)

1. I created the deck object with keys that are equal to the values of cards in API. It is 13 cards that we want to display on the screen. The values of the deck object I created are objects too, that consist of a numeric value and an empty URL (because we need to bind a numeric value with the image URL from API.)



2. I fetched data from the "Deck of Cards" API. I bonded properties of the deck object with values in API and pushed URLs of its values to my object.





3. I learned how to grab object values with Object.values method. I needed it to iterate over the values to fetch a particular card object from the deck object.



4. I made the getRandomCard function return an object with a random value and a random URL (we've got an array of URLs, because we've got cards of different suits).



5. In my game you won't meet two equal cards. Fo that I learned how to compare objects and It turned out to be not as simple as you may guess. We can't compare objects with a comparison operator, because it will compare only references of objects, but we need to compare the whole objects with their content. To accomplish that I created a separate function that uses a shallow comparison (a comparison of simple objects, without nested objects). I compared objects in the startGame function and in the newCard function. 



6. While in the startGame function I compared 2 objects between themselves, in the newCardfunction I compared a newly drawn card with the cards array. For that, I learned a new array method called "some", which returns a boolean if at least one element in the provided array passes the test implemented by the provided shallow comparison function.



7. Of course there should not be a game without a prize for a winner or some sign that you lose the game. So I decided to conditionally render some gifs in the end.



8. I conditionally changed the cards' left and top margins to create the effect when the cards overlap each other. I made it so each newly appearing card would have a top margin greater than the previous one, but the left margin is consistent from card to card.

![](/assets/blog/conditional styling.png)

Useful websites:



https://dmitripavlutin.com/how-to-compare-objects-in-javascript/

https://www.deckofcardsapi.com/





Some useful takeaways and hints:



1. querySelector is a more dynamic way to grab elements



2. An array is 0-indexed



3. DRY principle - Don't Repeat Yourself



4. When rendering the result of the "for loop" to the DOM, we should remember, that for loop clears everything before the final iteration. So to render  all iterations, don't forget the += 



Ex.(for (let i =0; i < sentence.length; i++) { 

greetingEl.textContent += sentence\[i] +" "}
