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

## Creating Columns

By default, grids contain only one column. If you were to start adding items, each item would be put on a new row; that’s not much of a grid! To change this, we need to explicitly define the number of rows and columns in our grid.

We can define the columns of our grid by using the CSS property grid-template-columns. Below is an example of this property in action:
```
.grid {
  display: grid;
  width: 500px;
  grid-template-columns: 100px 200px;
}
```
This property creates two changes. First, it defines the number of columns in the grid; in this case, there are two. Second, it sets the width of each column. The first column will be 100 pixels wide and the second column will be 200 pixels wide.

We can also define the size of our columns as a percentage of the entire grid’s width.
```
.grid {
  display: grid;
  width: 1000px;
  grid-template-columns: 20% 50%;
}
```
In this example, the grid is 1000 pixels wide. Therefore, the first column will be 200 pixels wide because it is set to be 20% of the grid’s width. The second column will be 500 pixels wide.

We can also mix and match these two units. In the example below, there are three columns of width 20 pixels, 40 pixels, and 60 pixels:
```
.grid {
  display: grid;
  width: 100px;
  grid-template-columns: 20px 40% 60px;
}
```
Notice that in this example, the total width of our columns (120 pixels) exceeds the width of the grid (100 pixels). This might make our grid cover other elements on the page! In a later exercise we will discuss how to avoid overflow.

## Creating Rows
We’ve learned how to define the number of columns in our grid explicitly. To specify the number and size of the rows, we are going to use the property grid-template-rows.

This property is almost identical to grid-template-columns. Take a look at the code below to see both properties in action.
```
.grid {
  display: grid;
  width: 1000px;
  height: 500px;
  grid-template-columns: 100px 200px;
  grid-template-rows: 10% 20% 600px;
}
```
This grid has two columns and three rows. grid-template-rows defines the number of rows and sets each row’s height. In this example, the first row is 50 pixels tall (10% of 500), the second row is 100 pixels tall (20% of 500), and the third row is 600 pixels tall.

When using percentages in these two properties, remember that rows are defined as a percentage of the grid’s height, and columns are defined as a percentage of its width.
