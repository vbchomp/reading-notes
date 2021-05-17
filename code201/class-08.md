# Class 08 - Layout

[<== Main Page](../README.md)

## *HTML Book* Chapter 15

- Block level elements start on new lines <h1> <p> <ul> <li>

- Inline elements flow in between surrounding text <img> <b> <i>

- Parent element or containing element is used to group together inside a block level element like a <div>

- Element positions
  - Normal
  - Relative shifts left, right, top or bottom of where it should have been
  - Absolute taken out of normal flow and does not affect surrounding elements, think headins that stay while scrolling down page
  - Fixed is a form of absolute that positions element in relation to browser not the containing element. Does not affect surrounding elements. Do not move on scrolls.
  - Floating becomes a block level element that other elements flow around

- Z-index property allows you to control which box appears on top

- Create floats with columns
  - `<div class="column1of2">`
  
```render-css
  
  .column1of2 {
    float: left;
    width: 620px;
    margin:10px;}
```

- Fixed width layout advantages
  - Pixel values accurate
  - Greater control of positioning and appearance
  - Control of lengths of texts regardless of size of windows
  - Size of images are always the same

- Liquid layout advantages
  - No spaces around the page on large screen
  - Page can contract to fit without having to scroll for smaller screens

- 960 Pixel Grid
  - Creates continuity between pages
  - Helps users predicts where to find info
  - Makes it easier to add new content consistently
  - Helps people collaborate on one site
  - 12 column grids use 60px columns, each column margin is 10px, which makes a 20px gap between each column, and 10px on the left and right hand sides of the page

- CSS Frameworks
  - Common code for repetitive tasks , like creating layout grids, styling forms, fronter-friendly pages
  - Means you need to use class names in HTML code that only controls the presentation of page or bloat

- 960.GS Grid Framework
  - *www.960.gs* free style sheet with framework
  - 12 column grid creation, needs an element that contains the whole page given the class attribute value of *container_12*. This sets the content of the page to 960 pixels wide and 12 column grid
  - Different classes for the blocks that make up 1, 2, 3, 4, and all the way up to 12 columns of the grid. Each blcok uses class names like grid_3 (stretches over 3 columns) all the way up to grid_12 which stretches all the way across the page.
  - These columns all float left with a 10px left and right margin
  - Other grid frameworks are available online, like at blueprintcss.org, lessframework.com, developer.yahoo.com/yui/grids/

- Using the 960.GS
  - HTML block level class of container_12 (sets up the 12 columns) and a attribute class of grid_X (where X indicates the amount of columns the each element will use)
  - Clearfix is needed in the container_12 to fix the height of the containing box to fix float issue of floats intruding in other columns.
  - Then in CSS set the height of any non full page grids, set font and background, and a margin on top and bottom (see pg 394 (HTML book))

- Using multiple CSS sheets
  - Can set up style sheets to control different elements of each site.
  - In HTML link the main and then on style sheet use @import `@import url("tables.css");` (these should be before other css rules)
  - Or link to each style sheet in HTML
