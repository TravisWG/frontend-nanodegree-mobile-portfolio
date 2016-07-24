## Website Performance Optimization portfolio project

This is my Performance Optimization portfolio project.  The object of this project was to take a website with some major performance issues and, using developer tools, find and resolve those issues.  Below I have outlined some major areas in each file that I changed to improve load times and performance of the various pages.

The main page can be accessed by simply opening index.html in a web browswer.

There are two distinct directories.
	/src contains the original site before performance improvements were made.
	/dist contains the improved site.

## index.html

	- Inlined some key portions of CSS at the top of the hmtl file
	- Put the remaining CSS files at the bottom to prevent render blocking
	- Add separate CSS file for mobile and added a media query so it would only load on mobile
	- Moved script tag to bottom of page and made files load asynchronously to prevent parser blocking of the DOM

## /views/js/main.js

	- refactored updatePositions() so it wasn't calling document during every iteration of the for loop
	- refactored changePizzaSizes():
		- so it wasn't calling document during every iteration of the for loop
		- so it wasn't reading Layout properties during every iteration of the for loop and caused Forced Synchronous Layout
	- changed the amount of sliding pizzas to be loaded based on the height of the viewport and reduced # of columns to 6
		* this could be made to be refreshed (currently will not change pizza amount in cases where browser window is resized)

## /views/css/style.css
	- added "will-change: transform" to .mover so the browswer will create background on separate layer

## images

	- large images in /img and /views/images were compressed and resized to improve load times