# CSS (Cascading Style Sheets)

## Introduction to CSS

- CSS stands for Cascading Style Sheets
- It's a language used to specify how things should look on a website
- CSS allows separation of styling from content (HTML)

### Types of Style Sheet Languages

- CSS (most important and widely used)
- Sass (Syntactically Awesome Style Sheets)
- Less (Leaner CSS)

## Adding CSS to HTML

There are three ways to add CSS to an HTML document:

1. Inline CSS
   - Applied directly to HTML elements using the style attribute
   - Useful for styling a single element
   - Example:
     ```html
     <p style="color: blue;">This is a blue paragraph.</p>
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
         }
       </style>
     </head>
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
     h1 {
       color: green;
     }
     ```

## CSS Selectors

CSS selectors are used to target specific HTML elements for styling:

### Element Selector
- Selects all elements of a specified type
- Syntax: Just use the element name
- Example: `h1 { color: blue; }`

### Class Selector
- Selects elements with a specific class attribute
- Syntax: Use a dot (.) followed by the class name
- Can be applied to multiple elements
- Example: `.highlight { background-color: yellow; }`

### ID Selector
- Selects a single element with a specific id attribute
- Syntax: Use a hash (#) followed by the id name
- Should be unique within a page
- Example: `#header { font-size: 24px; }`

### Attribute Selector
- Selects elements based on an attribute or attribute value
- Syntax: Use square brackets []
- Example: 
  ```css
  [draggable] { cursor: move; }
  [draggable="true"] { opacity: 0.8; }
  ```

### Universal Selector
- Selects all elements on the page
- Syntax: Use an asterisk (*)
- Example: `* { margin: 0; padding: 0; }`

### Combining Selectors
- You can combine different types of selectors for more specific targeting
- Example: `p.highlight { font-weight: bold; }`

## Basic CSS Concepts

### Properties and Values

- Properties define what aspect of the element to style (e.g., color, font-size)
- Values specify how to style the property (e.g., red, 16px)

### CSS Rule Structure

```css
selector {
  property: value;
}
```

## Basic Styling

### Text Styling

- font-family: Sets the typeface
- font-size: Adjusts the text size
  - Can be specified in various units:
    - px (pixels): 1px ≈ 1/96th of an inch (0.26mm)
    - pt (points): 1pt ≈ 1/72nd of an inch (0.35mm)
    - em: Relative to the parent element's font size
    - rem: Relative to the root element's font size
  - Example: `font-size: 16px;` or `font-size: 1.2rem;`
- font-weight: Sets the thickness of characters
  - Values: normal, bold, 100-900 (100 being thinnest, 900 being boldest)
  - Example: `font-weight: bold;` or `font-weight: 700;`
- color: Sets the text color
- text-align: Aligns text within its container
  - Values: left, right, center, justify
  - Example: `text-align: center;`

### Box Model

- margin: Space outside the element
- border: Line around the element
- padding: Space inside the element, between content and border
- width/height: Dimensions of the content area

### Colors

- Can be specified using:
  - Color names (e.g., red, blue)
  - Hexadecimal values (e.g., #FF0000)
  - RGB values (e.g., rgb(255, 0, 0))
  - RGBA values for transparency (e.g., rgba(255, 0, 0, 0.5))

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

## Layout

### Display Property

- block: Takes up full width, starts on a new line
- inline: Takes up only necessary width, doesn't start on a new line
- inline-block: Combines features of both inline and block

### Positioning

- static: Default positioning
- relative: Positioned relative to its normal position
- absolute: Positioned relative to nearest positioned ancestor
- fixed: Positioned relative to the viewport

### Flexbox

- Flexible Box Layout for efficient space distribution
- Main properties:
  - display: flex
  - flex-direction
  - justify-content
  - align-items

### Grid

- Two-dimensional layout system
- Main properties:
  - display: grid
  - grid-template-columns
  - grid-template-rows
  - grid-gap

## Responsive Design

### Media Queries

- Allow different styles for different device sizes
```css
@media screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

### Flexible Images

```css
img {
  max-width: 100%;
  height: auto;
}
```

### Viewport Meta Tag

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## Best Practices

- Use meaningful class and ID names
- Organize CSS with comments and consistent formatting
- Minimize use of !important
- Use shorthand properties when possible
- Consider using CSS methodologies (e.g., BEM, SMACSS) for larger projects

## CSS Frameworks

- Bootstrap: Popular framework for responsive, mobile-first design
- Tailwind CSS: Utility-first CSS framework
- Foundation: Responsive front-end framework

## Custom Fonts

- Use Google Fonts for a wide selection of free, web-safe fonts
- Steps to use Google Fonts:
  1. Go to fonts.google.com and select desired fonts
  2. Copy the provided \<link> tag and paste it in the \<head> of your HTML
  3. Use the provided CSS rule to apply the font to your elements
- Example:
  ```html
  <head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
  </head>
  ```
  ```css
  body {
    font-family: 'Roboto', sans-serif;
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
  - Changes in Developer Tools are temporary and don't affect the actual website