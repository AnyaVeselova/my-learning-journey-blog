---
title: Mobile ordering app
description: dfsdfsd
author: Anna Veselova
repoName: Mobile-restaurant-menu-solo
date: 2023-05-01T22:32:54.948Z
tags:
  - post
  - featured
image: /assets/blog/mobile-order.png
imageAlt: fdsfds
---

The Mobile ordering app is a Solo project, by building which I trained essential JS concepts, such as:

![](/assets/blog/essential_js.png)

... and many more, as I accomplished some stretch goals.

How did I build it?

This web app was built using HTML/CSS/SASS and JavaScript. I also used a bit of the Gulp task manager for the first time, but I used it mainly to watch scss and css files and compile the first one automatically.

I used the forEach array method to iterate over the data and created HTML string for each menu item. After that, I created a function that added reviews and basket HTML modules to the menu module in the "display:none" state, because we need them to appear when different events happen.

The showBasket function deals with the above. It receives an id of a particular menu item, that was clicked (the argument is passed to the function from the event listener on the document, where I provided the event dataset attribute).

With the help of the showBasket function, I found the clicked menu object and then created another HTML string, using the data of the found object. I changed the total cost in a basket module by adding to it the price of the menu item object. After that, I changed the innerHTML of the basket module and its visibility. I also changed the visibility of a reviews module to "none", because we want it to disappear when the basket module is visible.

The removeProduct function, which also receives its id similar to showBasket function, removes a product from the basket section when the remove button is clicked. Using this function I found a basket list item and removed it. The function also extracts the price of the removed item from the total variable and if it equals 0, it hides the whole basket module.

At the "checkout" state (when buyBtn is clicked) appears the form. I made the form accessible by using required attribute on its inputs. On its submission, I hide the form and create a new HTML string, that changes the basket layout into the rating layout.

Stretch goals:

Rating layout.

The rating layout allows a user to leave the review by writing it in a textarea field and also to rate their order with a star rating. It consists of a div, that contains 5 stars in its anchor tags and a review form with a textarea and a button. Each star link has its uuid, which enables us to save the state of each star when a user manipulates it. In the review form, I create an object, that consists of a user name, review text, and stars html string. I push it into the array of objects that was created earlier. I need that object to be able to render that review on the product page after the review form submission. I also saved the reviewsObj array to the local storage at this point, so the reviews can be present on the page even when the page refreshes. After that, I render the form.

Functioning rating stars:

To make rating stars functional and to make them change their opacity from 50% to 100% when one of them is clicked (and also to change the opacity of the stars before the one that was clicked), I found out next solution:

![](/assets/blog/stars_code.png)

I grabbed all of the stars and placed them in the array, then I iterated over the array with forEach method and assigned 50% opacity to each star.

After that, I found the star that was clicked by using the star's dataset. I found the index of the star. And the last part of the code is the part I'm most proud of: I used the decrementing for loop to change the opacity of the stars before the clicked one.

What does the render function do?

Basically, it makes the whole app appear on the page. It assigns the total variable to 0, so we can have an empty basket on a page refreshing. It conditionally renders our reviews on the page, depending on their presence in the local storage. It creates and adds a review list item to the reviews list, by iterating over each saved object in the local storage and putting the object data into HTML string. It makes the checkout form appear if the buyBtn was clicked.

What were some of the design decisions?

I decided to make a navigation background slide. I use JS to achieve that:

![](/assets/blog/navigation_slider.png)

The slider effect is achieved by assigning the display: "block" value to each slide in an increasing for loop, while assigning the display: "none" value to the previous slide outside of the loop.

What did I learn?

I learned a lot because I was doing the project on my own. The slider and rating stars were completely new things for me to implement.

While making the app, I also decided to learn SASS in parallel. I used the https://netninja.dev/ help. He has an amazing SASS course. It's called "Learn SASS & Build Your Own CSS Library". For my small project, I used only variables, partials, some nested rules, Math, parent selectors, and several mixins. In the future, I'm going to continue with SASS progression, and I'm looking forward to creating a grid system with it.
