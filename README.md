# CSS Grid

- CSS Grid is an advanced 2-Dimensional layout system
- Can layout entire websites or small components of websites
- Describes fixed and flexible track areas
- Allows for precise item placement within areas
- Provides for alignment of items
- Supports separate and overlapping items

---

# Grid Layout Codepen

<p data-height="450" data-theme-id="light" data-slug-hash="zmpdqb" data-default-tab="css,result" data-user="Dangeranger" data-pen-title="CSS Grid Layout - Template Areas" class="codepen">See the Pen <a href="https://codepen.io/Dangeranger/pen/zmpdqb/">CSS Grid Layout - Template Areas</a> by Joshua Burke (<a href="https://codepen.io/Dangeranger">@Dangeranger</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

---

# Basic Grid Example

```html

<div class="wrapper">
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
  <div>Four</div>
  <div>Five</div>
</div>
```

```css
.wrapper {
  display: grid;
  grid-template-columns: 200px 200px 200px;
}
```

---

# Basic Grid Codepen

<p data-height="407" data-theme-id="light" data-slug-hash="ZqvJbM" data-default-tab="css,result" data-user="Dangeranger" data-pen-title="Basic Grid Example" class="codepen">See the Pen <a href="https://codepen.io/Dangeranger/pen/ZqvJbM/">Basic Grid Example</a> by Joshua Burke (<a href="https://codepen.io/Dangeranger">@Dangeranger</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

---

# Grid Setup Explained

The CSS display property `grid` will create a grid container. It is very common to use a `div` as your container element since `div`s are a very unopinionated element. You should also feel free to use more descriptive HTML5 elements such as `main` `sidebar` `header` `footer` elements for different sections of your page. Grid containers:

* Contain the elements you want to lay out on the page
* Allow your container to set grid properties
  * grid properties determine how your elements are laid out *inside* the container
* Only operate on their direct child elements
* Align items based on the defined rows, and columns

---

# Grid Template Rows and Columns

To define the areas of your grid you can use the properties `grid-template-rows` and `grid-template-columns`. Both can take similar values, and are used to determine how many rows, and columns your grid has as well as their sizes.

```css
#grid-container {
  display: grid;
  grid-template-rows: 2fr 1fr 3fr 2fr;
  grid-template-columns: 1fr 2fr 1fr 1fr;
}
```

---

# grid-template-rows

* Usually optional; *if* it's not set your grid will:
  * make enough rows to fit your content
  * automatically make evenly sized rows
* Necessary *if* you want to set different sizes for different rows

---

# grid-template-columns

* Always necessary
* Used to determine how many, and what size your columns are
* If it's not set it will only make a single column
  * We have a better tool for unidirectional layout we'll be covering later

---

# The Grid Gap

* Defines the space *between* the cells of the grid
* `column-gap` defines the space between columns
* `row-gap` defines the space between rows
* `gap` is a shorthand property that combines `column-gap` and `row-gap`

---

# Assigning Elements to Areas

By default the child elements in a grid container will each fill one cell, going left to right, top to bottom in the order they are defined in your HTML. We can make the elements span multiple cells by using the `grid-column` and `grid-row` properties to determine exactly which cells an item is contained by. To specify cells you can give your `grid-column` and/or `grid-row` a starting line number, and either an ending line number, or a number of cells to span.

* Items can overlap
* All grid areas must by rectangular
* You can use `grid-column` and `grid-row` individually or in conjunction to specify grid areas

---

# An Excellent Reference

css-tricks.com is one of the best resources for all things CSS.

[Here's a handy reference guide for using CSS Grids](https://css-tricks.com/snippets/css/complete-guide-grid/)

---

# Let's play a game!

Let's practice some more grid setup! [Grid Garden](https://cssgridgarden.com/) Is a fantastic game that lets you practice using grid properties. Go there now, and see if you can complete all 28 levels!

---

# CSS Responsive Layout

* **Responsive** means that the layout **changes** and responds based on the width of the screen
* This allows for specific layouts for mobile phones, tablets, screen readers, and more
* Layouts can be rendered conditionally based on:
  * Screen size
  * Pixel density
  * Screen orientation
  * Height/Width ratio

Why might this be important?

---

## What is Responsive Development?

* Responsive development is a technique that displays content well regardless of the device it is being viewed on
* This concept is increasingly important, not all users are desktop browsers
* In 2017 and 2018 more than 50% of web traffic was from mobile devices, and that trend is only increasing.

---

## Responsive Units of Measurement

The easiest way to start making your sites mobile responsive is by using units of measurement that can change, especially for widths.

* Percentages - `50%`
* Viewport width - `vw`
* Viewport height - `vh`
* Root element font-size - `rem`
* Parent font-size - `em`

Why might width be more important than height when making sites responsive?

---

## Responsive Layout: Media Queries

* CSS3 introduced media queries, which allow developers to apply CSS properties to devices which match rules
* Media queries are the backbone of front-end responsive development with HTML and CSS
* Applying CSS to specific screen widths allows for changing the layout and styles based on the size of a device

---

## Mobile Device Simulator

![Mobile Device Simulation Screenshot](https://res.cloudinary.com/btvca/image/upload/v1574445189/curriculum/mobile-device-simulation_zlrmgj.png "Mobile Device Simulation Screeenshot")

---

## Documentation Links

[Link: Firefox Responsive Design Mode](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode "Firefox Responsive Design Mode")

[Link: Chrome Mobile Device Simulator](https://developers.google.com/web/tools/chrome-devtools/device-mode/ "Chrome Mobile Device Simulator")

---

## Using Media Queries

* Media Queries (`@media (some_condition) { }`) cause different CSS rules to be applied on different screens

This CSS will make our `.nav` element position relative when the media type is `print`

```css
// Default position layout
.nav {
  position: absolute;
}

// Print media only layout
@media print {
  .nav {
    position: relative;
  }
}
```

---

## Media Features

Each feature is a characteristic of the **user-agent**

| Query       | Description                                              |
|-------------|----------------------------------------------------------|
| width       | the width of the viewport                                |
| all         | TRUE if the device responds to media queries             |
| resolution  | Pixel density of the output device                       |
| color       | Number of bits per color component of the device         |
| pointer     | Is the primary input mechanism a pointing device         |
| hover       | Does the primary input mechanism allow the user to hover |

[MDN: Documentation on Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries "MDN Documentation on Media Queries")

---

## Media Query Conditionals - AND

Only change the layout to `position: relative;` when

* The media is `screen`
* AND
* The screen width is greater than or equal to 768 pixels

```css
@media screen and (min-width:768px) {
  .nav {
    position: relative;
  }
}
```

---

## Media Query Conditionals - OR

NOTE: OR is the `,` (comma) in a Media Query

Only change the layout to `position: relative;` when

* The media is `screen`
* OR
* The screen width is greater than or equal to 768 pixels

```css
@media screen, (min-width:768px) {
  .nav {
    position: relative;
  }
}
```

---

## Mobile-First Development

* Developing mobile first means to start styling out your web page for a mobile device, and then modify the layout for a desktop browser
* The result of this is modifying your CSS as screen sizes increase, rather than modifying your CSS as screen sizes decrease
* In other words, your media queries will be written for minimum widths, not maximum widths
* Tip: You can also set media queries in-between two screen sizes