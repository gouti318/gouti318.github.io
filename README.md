# Website Performance Optimization portfolio project #

## Instructions for use ##

1. unzip the zip file and then extract it to a folder.
2. The 'dist' is the folder containing the main minified source code used for rendering the website.
3. The 'src' is the folder containing the distribution code which is in user readable state and not minified.
4. Run index.html inside the 'dist' folder in any Web Browser to render the webpage.

## Steps to configure grunt ##

1. Install npm using node.js or any other similar means.
2. Install grunt either globally or specific to the project folder using npm install --save-dev grunt.
3. Go to the root folder containing the webpage and initialise the folder using npm init.
4. Using 'npm install' install all the necessary dependencies that are required. eg. grunt-contrib-cssmin etc.
5. Create a Gruntfile.js which will contain all the necessary steps the grunt should do automatically once run.
6. Now run grunt in the command prompt from the same directory to do the grunt functions.

## Optimisations done on index.html ##

* Inlined all the CSS assosciated with index.html (style.css)
* Resized and compressed the pizzeria and the profilepic image using grunt-responsive-images.
* Minified css and js that are not inlined using grunt-contrib-cssmin and grunt-contrib-uglify.
* Added async properties to the javascript to make it non render blocking.
* Added media="print" for the print.css file to make it non render blocking.
* Used webfont loader to load the googlefont and shifted it to the end of the HTML.

## Optimisations done on pizza.html ##

* Minified the css assosciated with the page using grunt-contrib-cssmin(style.css,bootstrap-grid.css).
* Minified the JavaScript assosciated with the webpage using grunt-contrib-uglify(main.js).
* Compressed and resized the pizzeria and pizza image using grunt-responsive-images.

## Optimizations done on main.js ##

* Changed the changeSliderLabel function by taking out the DOM accesing element out of the switch and initialised it to a variable pizzaSize.

* Made changes to the function changePizzaSizes by taking out the DOM accessing element from the for loop and initialised it to randomPizzaContainer.
* Removed Dx and instead used switch statements that returns percentage width required according to changes in size sliding bar.
* Removed the determineDx function as it was not used by any other function.
* Reduced no of pizza divisions from 100 to 50 and pulled document.getElementById out of the for loop.
* Created a new function onScroll to call the animation frame using a function onTick such that it only calls once per 10 frames are created and such that re-layout is not done using updatePositions. The onScroll function is called when the scroll event occurs on the page. The onScroll is also used to do one of the calculations that was previously done inside the for loop in updatePositions.
* Changed style.left to style.transform inorder to increase the speed.
* Reduced the number of sliding pizzas created in the event DOM content loaded from 200 to 30 as only that many pizzas are displayed on the screen at a time.
* Reset the elem.style.beginLeft to elem.style.left due to the use of style.transform.
