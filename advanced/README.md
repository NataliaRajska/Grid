# Introduction
In the previous lesson, you learned all the foundational properties necessary to create a two-dimensional grid-based layout for your web pages! In this lesson, you’ll learn the following additional properties that you can use to harness the power of CSS Grid Layout:

+ grid-template-areas
+ justify-items
+ justify-content
+ justify-self
+ align-items
+ align-content
+ align-self
+ grid-auto-rows
+ grid-auto-columns
+ grid-auto-flow

You will also learn about the explicit and implicit grids and grid axes.

## Grid Template Areas

The grid-template-areas property allows you to name sections of your web page to use as values in the grid-row-start, grid-row-end, grid-col-start,grid-col-end, and grid-area properties.
```
<div class="container">
  <header>Welcome!</header>
  <nav>Links!</nav>
  <section class="info">Info!</section>
  <section class="services">Services!</section>
  <footer>Contact us!</footer>
</div>
```
```
.container {
  display: grid;
  max-width: 900px;
  position: relative;
  margin: auto;
  grid-template-areas: "head head"
                       "nav nav" 
                       "info services"
                       "footer footer";
  grid-template-rows: 300px 120px 800px 120px;
  grid-template-columns: 1fr 3fr; 
}
 
header {
  grid-area: head;
} 
 
nav {
  grid-area: nav;
} 
 
.info {
  grid-area: info;
} 
 
.services {
  grid-area: services;
}
 
footer {
  grid-area: footer;
} 
```

You may want to expand this section of the website to view the code above more clearly.

1. In the example above, the HTML creates a web page with five distinct parts.
2. The grid-template-areas declaration in the .container rule set creates a 2-column, 4-row layout.
3. The grid-template-rows declaration specifies the height of each of the four rows from top to bottom: 300 pixels, 120 pixels, 800 pixels, and 120 pixels.
4. The grid-template-columns declaration uses the fr value to cause the left column to use one fourth of the available space on the page and the right column to use three-fourths of the available space on the page.
5. In each rule set below .container, we use the grid-area property to tell that section to cover the portion of the page specified. The header element spans the first row and both columns. The nav element spans the second row and both columns. The element with class .info spans the third row and left column. The element with class .services spans the third row and right column. The footer element spans the bottom row and both columns.
6. That’s it! An entire page laid out in 40 lines of code.
This property is declared on grid containers.

You can see what you’ll be building in this exercise here.

## Overlapping Elements

Another powerful feature of CSS Grid Layout is the ability to easily overlap elements.

When overlapping elements, it is generally easiest to use grid line names and the grid-area property.
```
<div class="container">
  <div class="info">Info!</div> 
  <img src="#" />
  <div class="services">Services!</div>
</div>
```
```
.container {
  display: grid;
  grid-template: repeat(8, 200px) / repeat(6, 100px);
}
 
.info {
  grid-area: 1 / 1 / 9 / 4;
}
 
.services {
  grid-area: 1 / 4 / 9 / 7;
}
 
img {
  grid-area: 2 / 3 / 5 / 5;
  z-index: 5;
}
```
In the example above, there is a grid container with eight rows and six columns. There are three grid items within the container — a <div> with the class info, a <div> with the class services, and an image.

The info section covers all eight rows and the first three columns. The services section covers all eight rows and the last three columns.

The image spans the 2nd, 3rd, and 4th rows and the 3rd and 4th columns.

The z-index property tells the browser to render the image element on top of the services and info sections so that it is visible.

## Justify Items

We have referred to “two-dimensional grid-based layout” several times throughout this course.

There are two axes in a grid layout — the column (or block) axis and the row (or inline) axis.

The column axis stretches from top to bottom across the web page.

The row axis stretches from left to right across the web page.

In the following four exercises, we will learn and use properties that rely on an understanding of grid axes.

**justify-items** is a property that positions grid items along the inline, or row, axis. This means that it positions items from left to right across the web page.

**justify-items** accepts these values:

+ start — aligns grid items to the left side of the grid area
+ end — aligns grid items to the right side of the grid area
+ center — aligns grid items to the center of the grid area
+ stretch — stretches all items to fill the grid area

There are several other values that justify-items accepts, which you can read about on the Mozilla Developer Network. The definitions for these values can also be found in the documentation. It is important to note that the page with the definitions includes some values that are not accepted in CSS Grid layout.
```
<main>
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
</main>
```
```
main {
  display: grid;
  grid-template-columns: repeat(3, 400px);
  justify-items: center;
}
```
In the example above, we use justify-items to adjust the positioning of some elements on this web page.

1. There is a grid container with three columns that are each 400 pixels wide.
2. The container has three grid items that do not have a specified width.
3. Without setting the justify-items property, these elements will span the width of the column they are in (400 pixels).
4. By setting the justify-items property to center, the .card <div>s will be centered inside of their columns. They will only be as wide as necessary to contain their content (the words Card 1, etc).
5. If we specify a width for the .card elements, they will not stretch the width of their column.
This property is declared on grid containers.

