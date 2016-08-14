# Website Performance Optimization Project

To run this file, visit https://github.com/daampofo/daampofo.github.io and Clone/Download the repository.

PageInsights has calculated a score of **90** for Mobile and **91** for Desktop.

## Part 1: Optimizing PageSpeed Insight score for index.html

**Optimizations:**

- Reduced the pizzeria.jpg size using optimizilla.com and renamed the file pizzeria-min.jpg
- Reduced the size of all images in image folders
- Minified style.css, renamed it style-min.css and inlined it to index.html
- Added async to the JS script tags and moved them to the bottom of index.html


## Part 2: Optimizing Frames per Second in main.js

**Optimization:**

- Reduced for-loop calculation by:
  - Placing (document.body.scrollTop / 1250) into a variable (`var top = document.body.scrollTop / 1250`) outside the loop but still in the updatePosition function.
  - Pushed items.length into variable (`var cachedLength = items.length`)
  - Created `var items` and placed it above the `var pizzaIngredients = {}`
  - items = documents.getElementsByClassName('mover') created and placed above updatePositions () because we only need to query items after they're made and before they need to be used. 
  - Created `var phase` and `var constArray`.
  - The for-loop contains constArray.push(Math.sin(top + i)); allowing it to run faster.
- Repositioned pizzas: 
  - `inserted items[i].style.transform = 'translateX(' + (100 * phase) + 'px)';`
- Replaced querySelector's with getElementById to increase scroll and page rendering.

## Part 3: Optimizing Pizza slider in main.js
- Replaced previous for-loop function with new loop.
- Added a switch case element to increase slider speed.
- Made `var randomPizzas` and changed the querySelectorAll element to getElementsByClassName.