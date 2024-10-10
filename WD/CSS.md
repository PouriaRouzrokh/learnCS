# CSS (Cascading Style Sheets)

## Introduction to CSS

- CSS stands for Cascading Style Sheets
- It's a language used to specify how things should look on a website
- CSS allows separation of styling from content (HTML)
- Example of separation:
  ```html
  <!-- HTML (Structure) -->
  <h1 class="title">Welcome to My Website</h1>
  ```
  ```css
  /* CSS (Style) */
  .title {
    color: navy;
    font-size: 24px;
    text-align: center;
  }
  ```

## Adding CSS to HTML

There are three ways to add CSS to an HTML document:

1. Inline CSS
   - Applied directly to HTML elements using the style attribute
   - Useful for styling a single element
   - Example:
     ```html
     <p style="color: blue; font-size: 16px; margin-left: 20px;">This is a blue paragraph with custom styling.</p>
     ```

2. Internal CSS
   - Defined within the \<style> tag in the HTML \<head>
   - Useful for styling a single web page
   - Example:
     ```html
     <head>
       <style>
         h1 {
           color: red;
           font-family: Arial, sans-serif;
         }
         .highlight {
           background-color: yellow;
           padding: 5px;
         }
       </style>
     </head>
     <body>
       <h1>This is a red heading</h1>
       <p class="highlight">This paragraph has a yellow background.</p>
     </body>
     ```

3. External CSS
   - Defined in a separate .css file and linked to the HTML
   - Most commonly used method, especially for multi-page websites
   - Example:
     ```html
     <head>
       <link rel="stylesheet" href="styles.css">
     </head>
     ```
     In styles.css:
     ```css
     body {
       font-family: Arial, sans-serif;
       line-height: 1.6;
       margin: 0;
       padding: 0;
     }
     h1 {
       color: green;
       text-align: center;
     }
     .container {
       width: 80%;
       margin: auto;
     }
     ```

## CSS Cascade

The cascade determines how conflicting CSS rules are resolved.

Order of importance (least to most):

1. Position
2. Specificity
3. Type
4. Importance

### Position
- Rules lower in the CSS file override earlier rules
```css
li { color: red; }
li { color: blue; } /* This rule will be applied */
```

### Specificity
Order (least to most specific):
1. Element selector
2. Class selector
3. Attribute selector
4. ID selector

Example:
```css
li { color: blue; }
.first-class { color: green; }
[draggable] { color: purple; }
#first-id { color: orange; /* This rule will be applied */ }
```

### Type
Order of importance:
1. External stylesheet
2. Internal stylesheet
3. Inline styles

### Importance
- Use `!important` to override all other rules
```css
p {
  color: red !important; /* This will override other color rules */
}
- Minimize use of !important
```

## CSS Selectors

CSS selectors target specific HTML elements for styling:

### Element Selector
- Selects all elements of a specified type
- Syntax: Just use the element name
```css
h1 { 
  color: blue;
  font-size: 24px;
}
```

### Class Selector
- Selects elements with a specific class attribute
- Syntax: Use a dot (.) followed by the class name
```css
.highlight { 
  background-color: yellow;
  padding: 5px;
}
```

### ID Selector
- Selects a single element with a specific id attribute
- Syntax: Use a hash (#) followed by the id name
```css
#header { 
  font-size: 24px;
  background-color: #f8f9fa;
}
```

### Attribute Selector
- Selects elements based on an attribute or attribute value
- Syntax: Use square brackets []
```css
[draggable] { 
  cursor: move;
}
```

### Universal Selector
- Selects all elements on the page
- Syntax: Use an asterisk (*)
```css
* { 
  margin: 0; 
  padding: 0;
}
```

## Combining CSS Selectors

CSS selectors can be combined for more precise targeting:

### Group Selector
- Syntax: `selector1, selector2`
```css
h1, h2 {
  color: blueviolet;
}
```

### Child Selector
- Syntax: `parent > child`
```css
.box > p {
  color: firebrick;
}
```

### Descendant Selector
- Syntax: `ancestor descendant`
```css
.box li {
  color: blue;
}
```

### Chaining Selectors
- Syntax: `selector1selector2` (no space)
```css
li.done {
  color: seagreen;
}
```

## CSS Box Model

Every HTML element is a box consisting of:

- Content: The actual content of the element
- Padding: Space between the content and the border
- Border: A line around the padding and content
- Margin: Space outside the border

Visual representation:
```
+-----------------------------------+
|              Margin               |
|   +---------------------------+   |
|   |          Border           |   |
|   |   +-------------------+   |   |
|   |   |      Padding      |   |   |
|   |   |   +-----------+   |   |   |
|   |   |   |  Content  |   |   |   |
|   |   |   +-----------+   |   |   |
|   |   +-------------------+   |   |
|   +---------------------------+   |
+-----------------------------------+
```

### Width and Height
- Control dimensions of content area
```css
.box {
  width: 300px;
  height: 200px;
}
.responsive-box {
  width: 50%;
  max-width: 500px;
  min-height: 100px;
}
```

### Border
- Syntax: `border: [width] [style] [color];`
- Can be modified for individual sides
```css
.box {
  border: 2px solid black;
}
.custom-border {
  border-top: 1px dashed red;
  border-right: 2px dotted green;
  border-bottom: 3px double blue;
  border-left: 4px groove orange;
}
```

### Padding
- Space between content and border
```css
.padded-box {
  padding: 20px; /* All sides */
}
.custom-padding {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 15px;
  padding-left: 25px;
}
```

### Margin
- Space outside the border
- Can use negative values to overlap elements
```css
.spaced-box {
  margin: 10px; /* All sides */
}
.custom-margin {
  margin-top: 20px;
  margin-right: auto; /* Center horizontally */
  margin-bottom: 30px;
  margin-left: auto;
}
```

## Basic Styling

### Text Styling

- font-family: Sets the typeface
  ```css
  body {
    font-family: Arial, Helvetica, sans-serif;
  }
  ```
- font-size: Adjusts the text size
  - Can be specified in various units:
    - px (pixels): 1px ≈ 1/96th of an inch (0.26mm)
    - pt (points): 1pt ≈ 1/72nd of an inch (0.35mm)
    - em: Relative to the parent element's font size
    - rem: Relative to the root element's font size
  - Example: 
    ```css
    h1 { font-size: 24px; }
    p { font-size: 1rem; }
    .large-text { font-size: 1.2em; }
    ```
  - Use appropriate units (px, %, em, rem) based on design needs
- font-weight: Sets the thickness of characters
  - Values: normal, bold, 100-900 (100 being thinnest, 900 being boldest)
  - Example: 
    ```css
    .bold-text { font-weight: bold; }
    .light-text { font-weight: 300; }
    ```
- color: Sets the text color
  ```css
  .error { color: #ff0000; }
  .success { color: rgb(0, 128, 0); }
  ```
- text-align: Aligns text within its container
  - Values: left, right, center, justify
  - Example: 
    ```css
    .centered { text-align: center; }
    .justified { text-align: justify; }
    ```

### Colors

- Can be specified using:
  - Color names (e.g., red, blue)
  - Hexadecimal values (e.g., #FF0000)
  - RGB values (e.g., rgb(255, 0, 0))
  - RGBA values for transparency (e.g., rgba(255, 0, 0, 0.5))
- Example:
  ```css
  .color-demo {
    color: red;
    background-color: #00ff00;
    border: 2px solid rgb(0, 0, 255);
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  }
  ```

#### Named Colors
- CSS provides a set of predefined color names
- Examples: red, blue, green, cornflowerblue, cadetblue, dimgrey, olivedrab
- Full list available in MDN Docs (search for "MDN Docs named color")

#### Hex Codes
- Represent colors using a combination of 6 characters (letters A-F and numbers 0-9)
- Example: #5D3891 (purple)
- Each pair of characters represents the intensity of red, green, and blue respectively

#### Color Selection Tools
- colorhunt.co: Provides professionally designed color palettes
- Useful for selecting complementary colors for website design

### Units

- Absolute units: px, pt, cm, mm, in
- Relative units: %, em, rem, vh, vw
- Example:
  ```css
  .container {
    width: 80%; /* Relative to parent */
    max-width: 1200px; /* Absolute */
    font-size: 16px;
  }
  .hero {
    height: 50vh; /* 50% of viewport height */
  }
  ```

### Typography

Use relative units for font sizes to ensure text remains readable on all devices.

```css
body {
  font-size: 16px; /* Base font size */
}

h1 {
  font-size: 2em; /* 2 times the base font size */
}

p {
  font-size: 1rem; /* Same as the root font size */
}
```

### Custom Fonts

- Use Google Fonts for a wide selection of free, web-safe fonts
- Steps to use Google Fonts:
  1. Go to fonts.google.com and select desired fonts
  2. Copy the provided \<link> tag and paste it in the \<head> of your HTML
  3. Use the provided CSS rule to apply the font to your elements
- Example:
  ```html
  <head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
  </head>
  ```
  ```css
  body {
    font-family: 'Roboto', sans-serif;
  }
  h1 {
    font-weight: 700; /* Bold */
  }
  p {
    font-weight: 300; /* Light */
  }
  ```

## Positioning

CSS positioning allows you to control the layout of elements on a web page. There are four main types of positioning:

1. **Static Positioning**
   - Default positioning for all HTML elements
   - Elements flow in the normal order of the HTML document
   - Properties like `top`, `bottom`, `left`, and `right` have no effect

2. **Relative Positioning**
   - Positions an element relative to its normal position
   - Use `top`, `bottom`, `left`, and `right` to offset from original position
   - Other elements are not affected by the positioned element
   ```css
   .relative-example {
     position: relative;
     top: 50px;
     left: 50px;
   }
   ```

3. **Absolute Positioning**
   - Positions an element relative to its nearest positioned ancestor
   - If no positioned ancestor, it's positioned relative to the initial containing block (usually the viewport)
   - Removed from the normal document flow
   - Other elements behave as if the absolutely positioned element doesn't exist
   ```css
   .absolute-example {
     position: absolute;
     top: 50px;
     left: 50px;
   }
   ```

4. **Fixed Positioning**
   - Positions an element relative to the browser window
   - Element stays in the same place even when the page is scrolled
   - Removed from the normal document flow
   ```css
   .fixed-example {
     position: fixed;
     top: 50px;
     right: 50px;
   }
   ```

### Z-index
- Controls the stacking order of elements
- Higher z-index values appear on top of elements with lower values
- Only works on positioned elements (not static)
```css
.stack-top {
  z-index: 100;
}
```

### Best Practices for Positioning
- Use relative positioning for minor adjustments
- Use absolute positioning sparingly, as it can complicate layouts
- Fixed positioning is useful for elements that should always be visible (e.g., navigation bars)
- Be cautious with z-index to avoid unintended overlapping

## Basic Layout

### Display Property: Block, Inline, and Inline-Block

The `display` property is crucial for controlling the layout of elements on a web page. There are three common types of display values:

#### Block
- Takes up the entire full width of the parent container
- Forces the next element to go below it
- Can have its width and height set
- Example: `<div>`, `<p>`, `<h1>`, `<form>`

#### Inline
- Only takes up as much width as its content requires
- Allows other elements to be on the same line
- Cannot have its width and height set
- Size is determined by its content
- Example: `<span>`, `<a>`, `<strong>`

#### Inline-Block
- Allows elements to be on the same line (like inline)
- Allows setting of width and height (like block)
- Useful for creating horizontally aligned elements with specific dimensions
- Example: `<img>`

#### Display: None
- Makes the element disappear from the page layout
- Useful for hiding elements dynamically (e.g., with JavaScript)

Example:
```css
.block { display: block; }
.inline { display: inline; }
.inline-block { display: inline-block; }
.hidden { display: none; }
```

## Responsive Layout

Responsive design is an approach to web design that makes web pages render well on a variety of devices and window or screen sizes. The goal is to create a single website that adapts to different viewing contexts, rather than creating separate designs for each type of device.

### Why Responsive Design is Important

1. Mobile device usage has surpassed desktop usage for web browsing.
2. Google uses mobile-first indexing for search rankings.
3. It provides a better user experience across all devices.
4. It's more cost-effective than maintaining separate mobile and desktop sites.

### Viewport Meta Tag

This tag ensures that the website is displayed correctly on mobile devices.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Media Queries

Media queries are a key technique for creating responsive designs. They allow you to apply different styles based on the characteristics of the device, primarily its width.

- Syntax: `@media screen and (max-width: 600px) { /* CSS rules */ }`
- You can define different styles for different screen sizes.

#### Key Concepts:

1. **max-width**: Targets screen sizes up to the specified width
   ```css
   @media (max-width: 600px) {
     h1 { font-size: 20px; }
   }
   ```

2. **min-width**: Targets screen sizes from the specified width and above
   ```css
   @media (min-width: 1200px) {
     .container { width: 1140px; }
   }
   ```

3. **Combining min-width and max-width**: Targets a specific range of screen sizes
   ```css
   @media (min-width: 600px) and (max-width: 900px) {
     .box { width: 50%; }
   }
   ```

4. **Targeting specific media types**:
   - `screen`: For computer screens (default if not specified)
   - `print`: For print preview mode/printed pages
   ```css
   @media print {
     .no-print { display: none; }
   }
   ```

#### Common Breakpoints:

While breakpoints should be determined by your content, here are some common ranges:

- Mobile devices: 319px - 480px
- iPads and tablets: 481px - 1200px
- Laptops: 1201px - 1600px
- Desktops: 1601px and above

Example of using these breakpoints:

```css
/* Base styles */
body { background-color: aquamarine; }

/* Mobile devices */
@media (max-width: 480px) {
  body { background-color: salmon; }
}

/* iPads and tablets */
@media (min-width: 481px) and (max-width: 1200px) {
  body { background-color: powderblue; }
}

/* Laptops */
@media (min-width: 1201px) and (max-width: 1600px) {
  body { background-color: limegreen; }
}

/* Desktops */
@media (min-width: 1601px) {
  body { background-color: seagreen; }
}
```

### Float

- Allows wrapping text around elements
- Primarily used for wrapping text around images in modern web design
- Syntax: `float: value;`
- Common values:
  - `left`: Floats element to the left
  - `right`: Floats element to the right

#### Usage
```css
img {
  float: left;
  margin-right: 10px;
}
```

#### Clear Property
- Used to prevent elements from wrapping around floated elements
- Syntax: `clear: value;`
- Common values:
  - `left`: Clears left floats
  - `right`: Clears right floats
  - `both`: Clears both left and right floats

#### Example
```css
.footer {
  clear: both;
}
```

#### Best Practices for Float
- Use float primarily for wrapping text around images
- Avoid using float for complex layouts
- Prefer modern layout techniques like Flexbox and Grid for complex designs

### Flexbox

Flexbox is a powerful CSS layout module designed to create flexible and responsive layouts easily. It provides a more efficient way to distribute space and align content within a container, even when the size of your items is unknown or dynamic.

#### Basic Concepts

- **Flex Container**: The parent element that holds flex items. Created by setting `display: flex` or `display: inline-flex`.
- **Flex Items**: The direct children of a flex container.
- **Main Axis**: The primary axis along which flex items are laid out. Defined by `flex-direction` (default is horizontal).
- **Cross Axis**: The axis perpendicular to the main axis.

#### Flex Container Properties

##### display

Defines a flex container.

```css
.container {
  display: flex; /* or inline-flex */
}
```

##### flex-direction

Establishes the main axis.

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

- `row`: Items are placed horizontally (default)
- `column`: Items are placed vertically
- `row-reverse` and `column-reverse`: Same as above but in reverse order

##### flex-wrap

Controls whether items should wrap or not if they exceed the container's size.

```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

- `nowrap`: All items on one line (default)
- `wrap`: Items wrap onto multiple lines
- `wrap-reverse`: Items wrap onto multiple lines in reverse

##### justify-content  

Aligns items along the main axis.

```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

- `flex-start`: Items at the start of the container
- `flex-end`: Items at the end of the container
- `center`: Items at the center
- `space-between`: Equal space between items
- `space-around`: Equal space around items
- `space-evenly`: Equal space between and around items

##### align-items

Aligns items along the cross axis.

```css
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

- `stretch`: Items stretch to fill the container (default)
- `flex-start`: Items at the start of the cross axis
- `flex-end`: Items at the end of the cross axis
- `center`: Items centered on the cross axis
- `baseline`: Items aligned by their baselines

##### align-content

Aligns multiple lines of content along the cross axis (only applies when there are multiple rows or columns of items).

```css
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

##### gap

Defines space between flex items.

```css
.container {
  gap: 10px; /* Sets both row-gap and column-gap to 10px */
  gap: 10px 20px; /* row-gap: 10px and column-gap: 20px */
}
```

#### Flex Item Properties

##### order

Controls the order of flex items.

```css
.item {
  order: 5; /* Default is 0 */
}
```

##### flex-grow

Defines the ability for a flex item to grow if necessary.

```css
.item {
  flex-grow: 1; /* Default is 0 */
}
```

##### flex-shrink

Defines the ability for a flex item to shrink if necessary.

```css
.item {
  flex-shrink: 1; /* Default is 1 */
}
```

##### flex-basis

Defines the default size of an element before the remaining space is distributed.

```css
.item {
  flex-basis: auto | <width>;
}
```

##### flex

Shorthand for flex-grow, flex-shrink, and flex-basis.

```css
.item {
  flex: none | [ <flex-grow> <flex-shrink>? || <flex-basis> ];
}
```

Common values:
- `flex: 1;` equivalent to `flex: 1 1 0%;`
- `flex: auto;` equivalent to `flex: 1 1 auto;`
- `flex: none;` equivalent to `flex: 0 0 auto;`

##### align-self 

Allows the default alignment to be overridden for individual flex items.

```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

#### Practical Example: Navigation Bar

Here's a simple example of a responsive navigation bar using Flexbox:

```html
<nav class="navbar">
  <div class="logo">MyWebsite</div>
  <ul class="nav-links">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  background-color: #333;
  color: white;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 1rem;
}

@media (max-width: 600px) {
  .navbar {
    flex-direction: column;
  }
  
  .nav-links {
    margin-top: 1rem;
  }
}
```

This example creates a horizontal navigation bar that switches to a vertical layout on smaller screens, demonstrating the power and flexibility of Flexbox for responsive design.

### Grid

#### Introduction to CSS Grid

- CSS Grid is a two-dimensional layout system designed for creating complex web layouts
- It allows precise control over both rows and columns simultaneously
- Complements Flexbox (one-dimensional layouts) for comprehensive layout control

#### Basic Grid Setup

- To create a grid container:
  ```css
  .container {
    display: grid;
  }
  ```
  This transforms the element into a grid container and its direct children into grid items.

- Defining rows and columns:
  ```css
  .container {
    grid-template-columns: 200px 200px 200px;
    grid-template-rows: 100px 100px;
  }
  ```
  This creates a 3x2 grid with fixed-size columns and rows.

#### Grid Terminology

- Grid Container: The element with `display: grid`
- Grid Items: Direct children of the grid container
- Grid Lines: The dividing lines that make up the structure of the grid
- Grid Tracks: The space between two adjacent grid lines (rows or columns)
- Grid Cell: The intersection of a row and a column
- Grid Area: The total space surrounded by four grid lines

#### Sizing Grid Tracks

1. Fixed sizes:
   ```css
   grid-template-columns: 100px 200px 300px;
   ```
   This creates three columns with exact pixel widths.

2. Fractional units (fr):
   ```css
   grid-template-columns: 1fr 2fr 1fr;
   ```
   The `fr` unit distributes available space proportionally. Here, the middle column gets twice the width of the others.

3. Auto keyword:
   ```css
   grid-template-columns: auto 200px auto;
   ```
   `auto` sizes the column based on its content, while still respecting other constraints.

4. Minmax function:
   ```css
   grid-template-columns: minmax(100px, 300px) 200px;
   ```
   `minmax(min, max)` sets a size range for the track. Here, the first column will be between 100px and 300px.

5. Repeat function:
   ```css
   grid-template-columns: repeat(3, 1fr);
   ```
   `repeat(count, size)` is a shorthand for repeating track sizes. This creates three equal-width columns.

#### Grid Gaps

- Set space between grid items:
  ```css
  .container {
    gap: 10px; /* Sets both row and column gaps */
    column-gap: 20px; /* Sets only column gaps */
    row-gap: 15px; /* Sets only row gaps */
  }
  ```

#### Positioning Grid Items

1. Grid-column and grid-row properties:
   ```css
   .item {
     grid-column: 1 / 3;
     grid-row: 2 / 4;
   }
   ```
   `grid-column` and `grid-row` define an item's location and span. The syntax is `start / end`, referring to grid lines.

2. Span keyword:
   ```css
   .item {
     grid-column: span 2;
   }
   ```
   `span` keyword tells the item to span a specific number of tracks. Here, it spans two columns.

3. Grid-area shorthand:
   ```css
   .item {
     grid-area: 1 / 2 / 3 / 4;
   }
   ```
   `grid-area` is shorthand for `row-start / column-start / row-end / column-end`.

#### Aligning Grid Items

- For the container:
  ```css
  .container {
    justify-items: center; /* Aligns items horizontally within their cell */
    align-items: center; /* Aligns items vertically within their cell */
  }
  ```

- For individual items:
  ```css
  .item {
    justify-self: end; /* Aligns this item horizontally within its cell */
    align-self: start; /* Aligns this item vertically within its cell */
  }
  ```

#### Responsive Grids

- Using auto-fit or auto-fill with minmax:
  ```css
  .container {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  ```
  `auto-fit` creates as many tracks as can fit in the container, each at least 200px wide, expanding to fill available space.

#### Nested Grids

- Grid items can be grid containers themselves:
  ```css
  .item {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  ```
  This creates a grid within a grid item, allowing for complex layouts.

#### Grid Areas

1. Defining named grid areas:
   ```css
   .container {
     grid-template-areas:
       "header header"
       "sidebar content"
       "footer footer";
   }
   ```
   This creates a named template for the grid layout.

2. Placing items in named areas:
   ```css
   .header { grid-area: header; }
   .sidebar { grid-area: sidebar; }
   .content { grid-area: content; }
   .footer { grid-area: footer; }
   ```
   Items are placed in their corresponding named areas.

#### Overlapping Grid Items

- Items can occupy the same grid cells:
  ```css
  .item1 { grid-area: 1 / 1 / 3 / 3; }
  .item2 { grid-area: 2 / 2 / 4 / 4; }
  ```
  This creates overlapping items, with `item2` partially covering `item1`.

#### Best Practices

- Use Grid for two-dimensional layouts, Flexbox for one-dimensional layouts
- Utilize Chrome Developer Tools to visualize and debug grid layouts
- Start with a mobile-first approach and use media queries for responsiveness
- Name grid lines for better readability:
  ```css
  .container {
    grid-template-columns: [start] 1fr [middle] 2fr [end];
  }
  ```
  This assigns names to grid lines, making it easier to reference them.

#### Example: Mondrian-style Layout

```html
<div class="container">
  <div class="item red"></div>
  <div class="item white1"></div>
  <div class="item white2"></div>
  <div class="item white3"></div>
  <div class="item blue"></div>
  <div class="item white4"></div>
  <div class="item"></div>
  <div class="item yellow"></div>
  <div class="item black"></div>
</div>
```

```css
.container {
  display: grid;
  grid-template-columns: 320px 198px 153px 50px;
  grid-template-rows: 414px 130px 155px 22px;
  gap: 9px;
  background-color: #000;
}

.white1 { grid-column: span 3; } /* Spans 3 columns */
.white2 { grid-row: span 2; } /* Spans 2 rows */
.white3 { grid-area: 2 / 2 / 4 / 4; } /* Starts at row 2, column 2, ends at row 4, column 4 */
.white4 { grid-row: span 2; } /* Spans 2 rows */
```

This example demonstrates how to create a complex, asymmetrical layout using CSS Grid. It showcases:
- Precise control over column and row sizes
- Use of the `span` keyword for multi-cell items
- The `grid-area` property for precise placement
- How Grid can recreate artistic designs in web layouts

By leveraging these Grid features, developers can create sophisticated layouts that would be challenging or impossible with other CSS layout methods.

### Bootstrap

## CSS Inspection

- Use Chrome Developer Tools to inspect and debug CSS
- Access Developer Tools:
  - Right-click and select "Inspect"
  - Use keyboard shortcuts (e.g., F12, Ctrl+Shift+I on Windows, Cmd+Option+I on Mac)
  - Go to More Tools > Developer Tools in Chrome menu
- Elements tab: Shows HTML structure and applied styles
- Styles section: Displays CSS rules for selected element
- Computed tab: 
  - Shows final applied styles after cascading
  - Utilize the "Computed" tab in Developer Tools to see final dimensions
- Features:
  - Select elements visually or via HTML structure
  - Add, modify, or disable CSS rules in real-time
  - Changes are temporary and don't affect the original files
  - Override existing styles and see conflicts
- CSS Overview (in More Tools):
  - Captures overview of colors, fonts, and other CSS properties used on the page
- Practical uses:
  - Debugging CSS issues
  - Experimenting with styles before implementing
  - Analyzing other websites' designs
- Tips:
  - Use the "+" button to add new CSS rules
  - Toggle rules on/off using the checkbox
  - Use the color picker to adjust colors visually
  - Experiment with values using arrow keys for fine-tuning
  - Use the "Box Model" visualization in Developer Tools


## General Best Practices

- Use meaningful class and ID names
  ```css
  /* Good */
  .main-navigation { ... }
  /* Avoid */
  .mn { ... }
  ```
- Organize CSS with comments and consistent formatting
  ```css
  /* Header Styles */
  header {
    background-color: #333;
    color: white;
    padding: 10px 0;
  }

  /* Main Content Styles */
  .main-content {
    margin: 20px 0;
  }
  ```
- Use shorthand properties when possible
  ```css
  /* Instead of */
  margin-top: 10px;
  margin-right: 15px;
  margin-bottom: 10px;
  margin-left: 15px;

  /* Use */
  margin: 10px 15px;
  ```
