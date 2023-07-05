---
title: Movie Watchlist Solo
description: >-
  This is a Solo project, that I built without assistance after completing
  "Async JS" module on Scrimba. It consists of 2 pages, one of which search
  movies by interacting with API database, and the other one renders movies you
  saved. Go to the article to find out how I made it. 
author: Anna Veselova
repoName: movie-watchlist-solo
date: 2023-05-01T22:53:38.163Z
tags:
  - post
image: /assets/blog/watchlist.png
imageAlt: gfdgfd
---
Welcome to the "Movie Watchlist" project.

**How did I build it?**

This project was built using HTML, CSS, JavaScript, and "The Open Movie Database" API (<https://www.omdbapi.com/>). The project has two pages (index.html and watchlist.html). Index.html is a search page, which calls to OMDB API with the title searched for and displays search results. Button "watchlist" in each rendered movie saves a movie to local storage. Watchlist.html, in its turn, loads and displays saved movies from local storage. 

**Going above and beyond:**

1. I created a "read more" button using JavaScript only. It allows a user to expand the whole movie review. To build that I set the limit to innerText.length of the element, containing the review text and rendered the button when the limit was exceeded. 

When the button is clicked, it toggles the "plot_trunc" CSS class, which truncates the text. The names of the buttons are also being replaced.

![null](/assets/blog/readmore.png)

2. As the devil is in the details, I made a search input to be triggered by the "Enter" key. This was accomplished with only 4 lines of code.

![null](/assets/blog/enter-save.png)

3. I animated the header background image and the "logo" paragraph using @keyframes (for the image I changed the background-position on different offsets, and for the title, I changed the opacity on different letters on different offsets, which created a flickering effect.)

**What did I learn?**

While building this project, I got to know **Async/Await syntax** and how to use it with promises. I also learned how to chain multiple promises and how to use the result of the 1st request in the 2nd request.
