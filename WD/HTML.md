# HTML Basics

## Heading Elements

- HTML uses heading elements to define content structure and hierarchy
- 6 levels of headings: \<h1> to \<h6>
- Syntax: \<h1>Heading content\</h1>

**Best practices for headings:**
- Use only one \<h1> per page (typically for the main title)
- Don't skip heading levels (e.g., don't go from \<h1> to \<h3> without using \<h2>)
- Arrange headings in a logical hierarchy

Example:
```html
<h1>Book</h1>
<h2>Chapter 1</h2>
<h3>Section 1</h3>
```

## Paragraph Elements

- Used for formatting and putting text on websites
- Syntax: \<p>Paragraph content\</p>
- Separates text into distinct paragraphs with line breaks

**Best practices for paragraphs:**
- Use for distinct blocks of text
- Ensure proper spacing for readability
- Consider accessibility (screen readers use paragraph breaks)

Example:
```html
<p>This is the first paragraph.</p>
<p>This is the second paragraph.</p>
```

## Void Elements

Elements that cannot contain content and have a single tag.

### Horizontal Rule (\<hr />)
- Creates a horizontal line, separating content
- Syntax: \<hr />

### Line Break (\<br />)
- Creates a line break within a paragraph
- Syntax: \<br />

**Best practices for void elements:**
- Use \<br /> for line breaks within a paragraph, not to create new paragraphs
- Use \<p> tags for separate paragraphs
- Consider using the self-closing syntax (\<br />) for clarity, though \<br> is also valid in HTML5

## List Elements

### Unordered Lists
- Created with \<ul> tag
- Used for lists where order doesn't matter
- List items represented by bullet points

### Ordered Lists
- Created with \<ol> tag
- Used for lists where order matters
- List items represented by numbers

### List Items
- Each item enclosed in \<li> tags
- Can contain text, images, or other HTML elements

**Best practices for lists:**
- Use appropriate list type (ordered vs. unordered)
- Nest lists for complex hierarchies
- Ensure proper indentation for readability

Example of a nested list:
```html
<ul>
  <li>Item A</li>
  <li>Item B
    <ol>
      <li>Subitem B1</li>
      <li>Subitem B2</li>
    </ol>
  </li>
  <li>Item C</li>
</ul>
```

## HTML Attributes

- Provide additional information about HTML elements
- Added to the opening tag of an element
- Syntax: attribute_name="value"

Types of Attributes:
1. Specific Attributes (unique to certain elements)
2. Global Attributes (can be used with any HTML element)

## Anchor Elements

- Used to create hyperlinks
- Tag: \<a>
- Requires the href attribute to specify the URL

**Best practices for anchor elements:**
- Use descriptive link text
- Ensure all links are functional
- Consider using the title attribute for additional information
- Use appropriate attributes (e.g., rel="noopener" for external links)

Example:
```html
<a href="https://www.example.com" target="_blank">Visit Example Site</a>
```

## Div Elements

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

## Image Elements

- Used to add images to websites
- Syntax: \<img src="url" alt="description" />
- Self-closing tag (void element)

**Best practices for image elements:**
- Always include the alt attribute for accessibility
- Use appropriate image formats (JPEG, PNG, GIF, etc.)
- Optimize images for web use to improve load times
- Consider using responsive images for different screen sizes

Example:
```html
<img src="https://picsum.photos/200/200" alt="Random image from Lorem Picsum" />
```

## HTML Table Tag

The `<table>` element in HTML was originally designed to display tabular data, but it was also widely used for creating web page layouts in the early days of web development.

### Table Structure
- `<table>`: The main container for the table
- `<tr>`: Table row
- `<td>`: Table data (cell)

### Historical Use for Layout
- Tables were used to create multi-column layouts
- Developers would set widths for columns and use nested tables for complex structures
- Example of a basic 3-column layout:
  ```html
  <table>
    <tr>
      <td width="25%">Left Column</td>
      <td width="50%">Middle Column</td>
      <td width="25%">Right Column</td>
    </tr>
  </table>
  ```

### Current Best Practices
- Use tables only for presenting tabular data, not for layout
- For layout purposes, use modern CSS techniques like Flexbox or Grid
- When using tables for data:
  1. Use `<th>` for table headers
  2. Use `<caption>` for table titles
  3. Consider using `<thead>`, `<tbody>`, and `<tfoot>` for better structure

### Accessibility Concerns
- Screen readers interpret table structures literally
- Using tables for layout can confuse assistive technologies
- Proper use of tables for data presentation enhances accessibility

### Styling Tables
- Use CSS for styling rather than deprecated HTML attributes
- Example:
  ```css
  table {
    width: 100%;
    border-collapse: collapse;
  }
  td, th {
    border: 1px solid #ddd;
    padding: 8px;
  }
  ```

While tables are still valid HTML elements, their use should be limited to presenting data that is truly tabular in nature. For layout purposes, modern CSS techniques provide more flexible and accessible solutions.

## File Paths

- Unique locations for files or folders on a computer
- Two types: Absolute and Relative paths

**Best practices for file paths:**
- Use relative file paths in web development
- Utilize VS Code's autosuggestion to avoid typing errors
- Test file paths by previewing the HTML file
- Understand the difference between ./ and ../
- Practice navigating complex folder structures

## Multi-page Websites

- Project folder contains all files for the website
- index.html is typically the home page
- Additional pages often placed in a 'public' folder

**Best practices for multi-page websites:**
- Organize files logically (e.g., images in an 'images' folder)
- Use clear, descriptive file names
- Test all links to ensure they work correctly
- Consider using a consistent navigation structure across all pages

## HTML Boilerplate

Basic structure for any HTML document:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
</head>
<body>
    <!-- Your content goes here -->
</body>
</html>
```

**Best practices for HTML boilerplate:**
- Use proper indentation for nested elements
- Include all necessary meta tags in the head section
- Use meaningful titles for your web pages
- In VS Code, type "!" and press Enter to automatically generate the boilerplate

## Web Hosting and GitHub Pages

- Web hosting makes websites available on the internet
- GitHub Pages is a free hosting service provided by GitHub

Steps to host with GitHub Pages:
1. Create a GitHub Account
2. Create a New Repository
3. Upload Your Website Files
4. Enable GitHub Pages
5. Access Your Live Website

**Best practices for web hosting:**
- Always use "index.html" as your home page filename
- Double-check that all files and folders are uploaded correctly
- Be patient, as GitHub Pages can take a few minutes to update
- If you encounter errors, try refreshing or waiting before trying again

## General Best Practices

- Use semantic HTML elements for better structure and accessibility
- Keep your HTML code clean and well-organized
- Regularly validate your HTML using tools like the W3C Markup Validation Service
- Stay updated with the latest HTML standards and best practices
- Comment your code when necessary for clarity
- Use CSS for styling instead of inline styles or deprecated HTML attributes
- Ensure your website is responsive and works well on various devices and screen sizes
- Test your website across different browsers for compatibility
- Consider using version control (like Git) to track changes in your code
- Regularly backup your website files and database (if applicable)