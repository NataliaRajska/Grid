Introduction to Grids
Using CSS, you can elegantly lay out elements on a web page. There is no simple answer for how best to do this — depending on what content you are trying to display, multiple different techniques can work well. Codecademy’s lessons on the box model and CSS display and positioning properties explain some possible ways to approach layout.

In this lesson, we introduce a new, powerful tool called CSS Grid. The grid can be used to lay out entire web pages. Whereas Flexbox is mostly useful for positioning items in a one-dimensional layout, CSS grid is most useful for two-dimensional layouts, providing many tools for aligning and moving elements across both rows and columns.

By the end of this lesson, you will understand how to use these properties to create grid layouts:

+ grid-template-columns
+ grid-template-rows
+ grid-template
+ grid-template-area
+ grid-gap
+ grid-row-start / grid-row-end
+ grid-column-start / grid-column-end
+ grid-area

That’s a lot to learn. But by the end, you’ll be a master at grid positioning. Let’s start learning!

**Note:** CSS Grid is supported in the most recent versions of many browsers, but it is not supported universally. To make sure that you can get the most out of this course, check your browser version and see if it supports CSS Grid. If CSS Grid is not supported in your browser, you should switch or update to a supported browser and version.

## Creating a Grid
To set up a grid, you need to have both a grid container and grid items. The grid container will be a parent element that contains grid items as children and applies overarching styling and positioning to them.

To turn an HTML element into a grid container, you must set the element’s display property to grid (for a block-level grid) or inline-grid (for an inline grid). Then, you can assign other properties to lay out the grid.
