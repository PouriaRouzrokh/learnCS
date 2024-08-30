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

## CSS Cascade

The cascade is a fundamental concept in CSS that determines how conflicting CSS rules are resolved.

### Order of Importance (from least to most important):

1. Position
2. Specificity
3. Type
4. Importance

#### Position

- Rules lower in the CSS file override earlier rules
- Example:
  ```css
  li {
    color: red;
  }
  li {
    color: blue; /* This rule will be applied */
  }
  ```

#### Specificity

Order of specificity (from least to most specific):
1. Element selector
2. Class selector
3. Attribute selector
4. ID selector

Example:
```css
li { color: blue; }
.first-class { color: green; }
[draggable] { color: purple; }
#first-id { color: orange; } /* This rule will be applied */
```

#### Type

Order of importance for CSS types:
1. External stylesheet
2. Internal stylesheet
3. Inline styles

#### Importance

- Use `!important` to override all other rules
- Example:
  ```css
  p {
    color: red !important; /* This will override other color rules */
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

## CSS Selectors

CSS selectors are used to target specific HTML elements for styling:

### Element Selector
- Selects all elements of a specified type
- Syntax: Just use the element name
- Example: 
  ```css
  h1 { 
    color: blue;
    font-size: 24px;
  }
  p {
    line-height: 1.5;
    margin-bottom: 15px;
  }
  ```

### Class Selector
- Selects elements with a specific class attribute
- Syntax: Use a dot (.) followed by the class name
- Can be applied to multiple elements
- Example: 
  ```css
  .highlight { 
    background-color: yellow;
    padding: 5px;
    border-radius: 3px;
  }
  .btn {
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    text-decoration: none;
    border-radius: 5px;
  }
  ```

### ID Selector
- Selects a single element with a specific id attribute
- Syntax: Use a hash (#) followed by the id name
- Should be unique within a page
- Example: 
  ```css
  #header { 
    font-size: 24px;
    background-color: #f8f9fa;
    padding: 20px;
    text-align: center;
  }
  #main-content {
    width: 70%;
    margin: auto;
  }
  ```

### Attribute Selector
- Selects elements based on an attribute or attribute value
- Syntax: Use square brackets []
- Example: 
  ```css
  [draggable] { 
    cursor: move;
  }
  [draggable="true"] { 
    opacity: 0.8;
  }
  [type="text"] {
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  ```

### Universal Selector
- Selects all elements on the page
- Syntax: Use an asterisk (*)
- Example: 
  ```css
  * { 
    margin: 0; 
    padding: 0;
    box-sizing: border-box;
  }
  ```

## Combining CSS Selectors

CSS selectors can be combined in various ways to target specific elements more precisely:

### Group Selector
- Syntax: `selector1, selector2`
- Applies the same style to multiple selectors
- Example:
  ```css
  h1, h2 {
    color: blueviolet;
  }
  ```

### Child Selector
- Syntax: `parent > child`
- Selects direct children of the parent element
- Example:
  ```css
  .box > p {
    color: firebrick;
  }
  ```

### Descendant Selector
- Syntax: `ancestor descendant`
- Selects all descendants of the ancestor element
- Example:
  ```css
  .box li {
    color: blue;
  }
  ```

### Chaining Selectors
- Syntax: `selector1selector2` (no space)
- Selects elements that match all chained selectors
- Example:
  ```css
  li.done {
    color: seagreen;
  }
  ```

### Combining Different Methods
- You can combine multiple selector methods
- Example:
  ```css
  ul p.done {
    font-size: 0.5rem;
  }
  ```

#### Best Practices for Combining Selectors
- Use specific selectors to avoid unintended styling
- Combine selectors to reduce repetition in your CSS
- Start with element selectors when chaining with classes or IDs
- Use descendant selectors for more flexibility than child selectors
- Utilize browser developer tools to verify your selector targets

## Basic CSS Concepts

### Properties and Values

- Properties define what aspect of the element to style (e.g., color, font-size)
- Values specify how to style the property (e.g., red, 16px)
- Example:
  ```css
  p {
    color: navy;
    font-size: 16px;
    line-height: 1.5;
    margin-bottom: 15px;
  }
  ```

### CSS Rule Structure

```css
selector {
  property1: value1;
  property2: value2;
  /* More properties and values */
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

### Box Model

- margin: Space outside the element
- border: Line around the element
- padding: Space inside the element, between content and border
- width/height: Dimensions of the content area
- Example:
  ```css
  .box {
    width: 200px;
    height: 100px;
    margin: 10px;
    border: 2px solid black;
    padding: 20px;
  }
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

## Layout

### Display Property

The `display` property is crucial for controlling the layout of elements on a web page. There are three common types of display values:

- `block`: Takes up full width, starts on a new line
- `inline`: Takes up only necessary width, doesn't start on a new line
- `inline-block`: Combines features of both inline and block

#### Block
- Takes up the entire full width of the parent container
- Forces the next element to go below it
- Can have its width and height set

#### Inline
- Only takes up as much width as its content requires
- Allows other elements to be on the same line
- Cannot have its width and height set
- Size is determined by its content

#### Inline-Block
- Allows elements to be on the same line (like inline)
- Allows setting of width and height (like block)
- Useful for creating horizontally aligned elements with specific dimensions

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

#### Best Practices for Display Property
- Use `block` for full-width elements or when you need to set specific dimensions
- Use `inline` for text-level elements that should flow within content
- Use `inline-block` when you need both inline behavior and the ability to set dimensions
- Experiment with different display values to achieve desired layouts
- Remember that `inline` elements ignore width and height properties

#### Practical Application
- Changing display properties can dramatically alter page layout without changing HTML structure
- `inline-block` is particularly useful for creating horizontal layouts with specific element sizes
- Use developer tools to experiment with display properties in real-time

### Positioning

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

#### Z-index
- Controls the stacking order of elements
- Higher z-index values appear on top of elements with lower values
- Only works on positioned elements (not static)
```css
.stack-top {
  z-index: 100;
}
```

#### Best Practices for Positioning
- Use relative positioning for minor adjustments
- Use absolute positioning sparingly, as it can complicate layouts
- Fixed positioning is useful for elements that should always be visible (e.g., navigation bars)
- Be cautious with z-index to avoid unintended overlapping

#### Creating Circles with CSS
You can create circular shapes using the `border-radius` property:
```css
.circle {
  width: 200px;
  height: 200px;
  background-color: red;
  border-radius: 50%;
}
```

Remember that positioned elements (except for static) can affect the positioning context for their descendants, which is crucial for creating complex layouts.

### Flexbox

- Flexible Box Layout for efficient space distribution
- Main properties:
  - display: flex
  - flex-direction
  - justify-content
  - align-items
- Example:
  ```css
  .flex-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .flex-item {
    flex: 1;
    margin: 5px;
  }
  ```

### Grid

- Two-dimensional layout system
- Main properties:
  - display: grid
  - grid-template-columns
  - grid-template-rows
  - grid-gap
- Example:
  ```css
  .grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 20px;
  }
  .grid-item {
    background-color: #f0f0f0;
    padding: 20px;
    text-align: center;
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

## Responsive Design

Responsive design is an approach to web design that makes web pages render well on a variety of devices and window or screen sizes. The goal is to create a single website that adapts to different viewing contexts, rather than creating separate designs for each type of device.

### Why Responsive Design is Important

1. Mobile device usage has surpassed desktop usage for web browsing.
2. Google uses mobile-first indexing for search rankings.
3. It provides a better user experience across all devices.
4. It's more cost-effective than maintaining separate mobile and desktop sites.

### Key Techniques for Responsive Design

#### 1. Media Queries

Media queries are a key technique for creating responsive designs. They allow you to apply different styles based on the characteristics of the device, primarily its width.

- Syntax: `@media screen and (max-width: 600px) { /* CSS rules */ }`
- You can define different styles for different screen sizes.

##### Key Concepts:

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

##### Common Breakpoints:

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

##### Testing Responsive Designs:

1. Use browser developer tools (e.g., Chrome DevTools):
   - Open Developer Tools (F12 or Ctrl+Shift+I / Cmd+Option+I)
   - Click on the device toolbar icon to simulate different screen sizes
   - Choose from preset device sizes or create custom dimensions
2. Resize the browser window
3. Test on real devices when possible

##### Best Practices:

1. Use a mobile-first approach: Start with styles for small screens, then add complexity for larger screens
2. Don't rely solely on device-specific breakpoints; adjust based on your content
3. Use relative units (%, em, rem) for flexible layouts
4. Combine media queries with flexible layouts (Flexbox or Grid) and responsive images
5. Keep your media queries organized and commented for easy maintenance

##### Advanced Usage:

You can target other features besides width, such as device orientation or aspect ratio:

```css
@media (orientation: landscape) {
  .sidebar { float: left; }
}

@media (aspect-ratio: 16/9) {
  .video-container { padding-bottom: 56.25%; }
}
```

Remember, media queries are just one part of responsive design. They work best when combined with a flexible layout system and responsive assets (like images and videos).

#### 2. Flexible Grid-Based Layout

CSS Grid and Flexbox are powerful tools for creating flexible, responsive layouts.

##### CSS Grid

CSS Grid is ideal for 2D layouts (rows and columns).

Example:
```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}
```

This creates a grid where:
- Columns are automatically created to fit the available space.
- Each column is at least 250px wide.
- Columns expand equally to fill extra space.
- There's a 20px gap between grid items.

As the screen size changes, the number of columns adjusts automatically.

##### Flexbox

Flexbox is great for 1D layouts (either rows or columns).

Example:
```css
.container {
  display: flex;
  flex-wrap: wrap;
}

.item {
  flex: 1 1 200px; /* grow | shrink | basis */
}
```

This creates a flexible layout where:
- Items are laid out in a row and wrap to the next line if needed.
- Each item has a minimum width of 200px but can grow or shrink as needed.

#### 3. Flexible Images

Images need to be flexible to fit different screen sizes.

```css
img {
  max-width: 100%;
  height: auto;
}
```

This ensures that images never exceed their container's width and maintain their aspect ratio.

#### 4. Typography

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

#### 5. Viewport Meta Tag

This tag ensures that the website is displayed correctly on mobile devices.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Responsive Frameworks

#### Bootstrap

Bootstrap is a popular CSS framework that includes a responsive grid system and pre-styled components.

Example of Bootstrap's grid system:
```html
<div class="container">
  <div class="row">
    <div class="col-sm-6 col-md-4 col-lg-3">
      <!-- Content here -->
    </div>
    <!-- More columns... -->
  </div>
</div>
```

This creates a column that's:
- Full width on extra small screens (< 576px)
- Half width on small screens (≥ 576px)
- One-third width on medium screens (≥ 768px)
- One-quarter width on large screens (≥ 992px)

### Best Practices for Responsive Design

1. Mobile-First Approach: Design for mobile devices first, then progressively enhance for larger screens.
2. Use Relative Units: Prefer percentage, em, rem over fixed pixel values.
3. Test on Real Devices: While browser dev tools are helpful, nothing beats testing on actual devices.
4. Consider Performance: Optimize images and minimize HTTP requests to ensure fast loading on mobile networks.
5. Touch-Friendly: Ensure interactive elements are large enough and have enough space for touch interactions.
6. Breakpoints: Choose breakpoints based on your content, not on specific devices.
7. Hide/Show Content Carefully: Be judicious about hiding content on smaller screens. Ensure critical information is always accessible.

By implementing these techniques and following best practices, you can create websites that provide an optimal viewing and interaction experience across a wide range of devices.

## CSS Frameworks

- Bootstrap: Popular framework for responsive, mobile-first design
  ```html
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  ```
- Tailwind CSS: Utility-first CSS framework
  ```html
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  ```
- Foundation: Responsive front-end framework
  ```html
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/foundation-sites@6.7.5/dist/css/foundation.min.css">
  ```

## Custom Fonts

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

## CSS Inspection

- Use Chrome Developer Tools to inspect and debug CSS
- Access Developer Tools:
  - Right-click and select "Inspect"
  - Use keyboard shortcuts (e.g., F12, Ctrl+Shift+I on Windows, Cmd+Option+I on Mac)
  - Go to More Tools > Developer Tools in Chrome menu
- Elements tab: Shows HTML structure and applied styles
- Styles section: Displays CSS rules for selected element
- Computed tab: Shows final applied styles after cascading
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
- Example of using Developer Tools:
  1. Right-click on an element and select "Inspect"
  2. In the Styles pane, click on a property value to edit it
  3. Add a new property by clicking on an empty line
  4. Use the Element State section to toggle pseudo-classes like :hover

## CSS Box Model and Layout

### Box Model Components

- Every HTML element is essentially a box
- Box model consists of:
  - Content: The actual content of the element (text, images, etc.)
  - Padding: Space between the content and the border
  - Border: A line around the padding and content
  - Margin: Space outside the border
- Visual representation:
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
- Can be set in pixels or percentages
- Example:
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
- Border-width can take up to 4 values (top, right, bottom, left)
- Examples:
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
  .border-shorthand {
    border-width: 1px 2px 3px 4px; /* top right bottom left */
    border-style: solid dashed dotted double;
    border-color: red green blue yellow;
  }
  ```

### Padding

- Space between content and border
- Can be set for all sides or individually
- Examples:
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
  .padding-shorthand {
    padding: 10px 20px 15px 25px; /* top right bottom left */
  }
  ```

### Margin

- Space outside the border
- Can be set for all sides or individually
- Can use negative values to overlap elements
- Examples:
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
  .margin-shorthand {
    margin: 10px 20px; /* 10px top/bottom, 20px left/right */
  }
  .negative-margin {
    margin-top: -10px; /* Pull element up */
  }
  ```

### Div Element

- Content Division Element
- Creates invisible boxes to group content
- Useful for layout and styling
- Example:
  ```html
  <div class="container">
    <div class="header">
      <h1>Welcome</h1>
    </div>
    <div class="content">
      <p>This is the main content.</p>
    </div>
    <div class="footer">
      <p>&copy; 2023 My Website</p>
    </div>
  </div>
  ```
  ```css
  .container {
    width: 80%;
    margin: 0 auto;
  }
  .header, .footer {
    background-color: #f0f0f0;
    padding: 20px;
  }
  .content {
    padding: 20px;
    border: 1px solid #ccc;
  }
  ```

### CSS Debugging

- Chrome extension "Pesticide" helps visualize div boxes and element boundaries
- Usage:
  1. Install the Pesticide extension from Chrome Web Store
  2. Click the Pesticide icon to toggle outlines on/off
  3. Each element will be outlined with a different color
- Alternative method using CSS:
  ```css
  * {
    outline: 1px solid red !important;
  }
  ```

### General Best Practices

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
- Minimize use of !important
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
- Consider using CSS methodologies (e.g., BEM, SMACSS) for larger projects

- Use appropriate units (px, %, em, rem) based on design needs
  ```css
  .container {
    width: 80%; /* Responsive width */
    max-width: 1200px; /* Maximum width */
    padding: 20px; /* Fixed padding */
  }
  .font-size {
    font-size: 1rem; /* Relative to root font size */
  }
  ```
- Consider box model when setting dimensions
  ```css
  .box-sizing-example {
    box-sizing: border-box; /* Include padding and border in width/height */
    width: 200px;
    padding: 20px;
    border: 2px solid black;
  }
  ```
- Group related content using div elements
  ```html
  <div class="card">
    <div class="card-header">
      <h2>Card Title</h2>
    </div>
    <div class="card-body">
      <p>Card content goes here.</p>
    </div>
    <div class="card-footer">
      <button>Learn More</button>
    </div>
  </div>
  ```
- Use CSS inspection tools for debugging layout issues
  - Utilize the "Computed" tab in Developer Tools to see final dimensions
  - Use the "Box Model" visualization in Developer Tools