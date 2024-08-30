# HTML Basics

## Heading Elements

- HTML uses heading elements to define the structure and hierarchy of content
- There are 6 levels of headings: \<h1> to \<h6>
- Syntax: \<h1>Heading content\</h1>
- Use only one \<h1> per page (typically for the main title)
- Don't skip heading levels (e.g., don't go from \<h1> to \<h3> without using \<h2>)
- Arrange headings in a logical hierarchy
```html
<h1>Book</h1>
<h2>Chapter 1</h2>
<h3>Section 1</h3>
```

## Paragraph Elements

- Used for formatting and putting text on websites
- Syntax: \<p>Paragraph content\</p>
- Separates text into distinct paragraphs with line breaks
- Important for readability and accessibility (screen readers)
```html
<p>This is the first paragraph.</p>
<p>This is the second paragraph.</p>
```

## Void Elements

- Elements that cannot contain content
- Have a single tag with a forward slash before the closing angle bracket
- Common void elements: horizontal rule (\<hr />) and line break (\<br />)

### Horizontal Rule (\<hr />)
- Used to create a horizontal line, separating content
- Syntax: \<hr />

### Line Break (\<br />)
- Used to create a line break within a paragraph
- Useful for formatting addresses, poems, etc.
- Syntax: \<br />

Best Practices:
- Use \<br /> for line breaks within a paragraph, not to create new paragraphs
- Use \<p> tags for separate paragraphs
- Consider using the self-closing syntax (\<br />) for clarity, though \<br> is also valid in HTML5

## List Elements

### Unordered Lists
- Created with \<ul> tag
- Used for lists where order doesn't matter (e.g., shopping lists)
- List items are represented by bullet points
- Syntax:
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

### Ordered Lists
- Created with \<ol> tag
- Used for lists where order matters (e.g., instructions)
- List items are represented by numbers
- Syntax:
```html
<ol>
  <li>First step</li>
  <li>Second step</li>
  <li>Third step</li>
</ol>
```

### List Items
- Each item in a list (ordered or unordered) is enclosed in \<li> tags
- Can contain text, images, or other HTML elements

## Nesting and Indentation

### Nested Lists
- Lists can be nested inside other lists
- Create complex hierarchies by placing a new \<ul> or \<ol> inside an \<li> element
- Example of a nested list:
```html
<ul>
  <li>Item A</li>
  <li>Item B
    <ol>
      <li>Subitem B1</li>
      <li>Subitem B2
        <ul>
          <li>Sub-subitem B2a</li>
          <li>Sub-subitem B2b</li>
        </ul>
      </li>
      <li>Subitem B3</li>
    </ol>
  </li>
  <li>Item C</li>
</ul>
```

### Importance of Indentation
- Proper indentation improves code readability
- Helps visualize the structure and hierarchy of nested elements
- Makes it easier to spot errors and debug code
- Most code editors (e.g., VS Code) can automatically format and indent HTML

### Best Practices
- Use consistent indentation (usually 2 or 4 spaces)
- Align opening and closing tags vertically when nesting
- Let your code editor help with automatic indentation
- Review indentation to understand code structure and find potential errors

## HTML Attributes

- Attributes provide additional information about HTML elements
- Added to the opening tag of an element
- Syntax: attribute_name="value"
- Multiple attributes are separated by spaces

### Types of Attributes

1. Specific Attributes
   - Unique to certain elements
   - Example: href for anchor elements

2. Global Attributes
   - Can be used with any HTML element
   - Examples: class, id, style, draggable

## Anchor Elements

- Used to create hyperlinks
- Tag: \<a>
- Requires the href attribute to specify the URL
- Syntax:
```html
<a href="https://www.example.com">Link Text</a>
```

### Key Attributes for Anchor Elements

- href: Specifies the URL of the linked page
- target: Determines where to open the linked document (e.g., _blank for a new tab)
- rel: Defines the relationship between the current page and the linked page

### Example of Nested Anchor Elements in Lists

```html
<ol start="5">
  <li><a href="https://www.example1.com">Favorite Website 1</a></li>
  <li><a href="https://www.example2.com">Favorite Website 2</a></li>
  <li><a href="https://www.example3.com">Favorite Website 3</a></li>
  <li><a href="https://www.example4.com">Favorite Website 4</a></li>
  <li><a href="https://www.example5.com">Favorite Website 5</a></li>
</ol>
```

### Best Practices

- Use descriptive link text
- Ensure all links are functional
- Consider using the title attribute for additional information
- Use appropriate attributes (e.g., rel="noopener" for external links)

## Ordered List Attributes

- start: Specifies the start value of an ordered list
  Example: \<ol start="5"> starts the list from number 5

## Image Elements

- Used to add images to websites
- Syntax: \<img src="url" alt="description" />
- Self-closing tag (void element)

### Key Attributes for Image Elements

- src: Specifies the source URL of the image
- alt: Provides alternative text description for accessibility

### Example
```html
<img src="https://picsum.photos/200/200" alt="Random image from Lorem Picsum" />
```

### Best Practices

- Always include the alt attribute for accessibility
- Use appropriate image formats (JPEG, PNG, GIF, etc.)
- Optimize images for web use to improve load times
- Consider using responsive images for different screen sizes

### Accessibility

- Screen readers use the alt text to describe images to visually impaired users
- Provide clear and concise descriptions in the alt attribute
- For decorative images, use an empty alt attribute (alt="") to skip them in screen readers

## File Paths

- File paths are unique locations for files or folders on a computer
- Two types: Absolute and Relative paths

### Absolute File Paths
- Relative to the root of the computer (e.g., C: drive or Macintosh HD)
- Example (Windows): C:\Project\Images\cat.png
- Example (Mac): /Users/username/Project/Images/cat.png
- Useful for navigating on a computer, regardless of current location

### Relative File Paths
- Relative to the current file's location
- More useful for web development
- Shorter and remain valid if folders are moved
- Example: Images/cat.png (if current file is in the Project folder)

### Special Characters in File Paths
- ../ : Go up one level in the directory structure
- ./ : Stay within the current directory
- Example using ../: ../essay.docx (to access a file in the parent directory)
- Example using ./: ./dog.png (to access a file in the current directory)

### Using File Paths in HTML
- For linking to other pages: \<a href="./about.html">About\</a>
- For images: \<img src="./assets/images/cat.png" alt="Cat image">

### Best Practices
- Use relative file paths in web development
- Utilize VS Code's autosuggestion to avoid typing errors
- Test file paths by previewing the HTML file
- Understand the difference between ./ and ../
- Practice navigating complex folder structures

## Multi-page Websites

### Structure
- Project folder contains all files for the website
- index.html is typically the home page
- Additional pages (e.g., about.html, contact.html) are often placed in a 'public' folder

### Linking Pages
- Use anchor tags with relative file paths to link between pages
- Example: \<a href="./public/about.html">About\</a>

### Embedding Images as Links
- Wrap an img tag inside an anchor tag
- Example:
  ```html
  <a href="./public/about.html">
    <img src="./assets/images/profile.jpg" alt="Profile picture">
  </a>
  ```

### Best Practices
- Organize files logically (e.g., images in an 'images' folder)
- Use clear, descriptive file names
- Test all links to ensure they work correctly
- Consider using a consistent navigation structure across all pages

## HTML Boilerplate

The HTML boilerplate is the basic structure for any HTML document. It includes:

### DOCTYPE Declaration
- Tells the browser which version of HTML the file is written in
- For HTML5: \<!DOCTYPE html>

### HTML Element
- Root element of the HTML page
- Contains lang attribute to specify the language of the text content
- Example: \<html lang="en">

### Head Element
- Contains metadata about the document
- Not displayed to the user
- Key components:
  - Character encoding: \<meta charset="UTF-8">
  - Viewport settings: \<meta name="viewport" content="width=device-width, initial-scale=1.0">
  - Title: \<title>My Website\</title>

### Body Element
- Contains the visible content of the webpage
- All text, images, links, and other elements go here

### Basic Structure
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

### Best Practices
- Use proper indentation for nested elements
- Include all necessary meta tags in the head section
- Use meaningful titles for your web pages
- In VS Code, type "!" and press Enter to automatically generate the boilerplate

### Nesting and Indentation
- HTML elements can be nested inside each other
- Proper indentation helps visualize the structure and hierarchy
- Example of nested elements:
  ```html
  <body>
    <h1>Welcome to My Website</h1>
    <div>
      <p>This is a paragraph inside a div.</p>
    </div>
  </body>
  ```
## Web Hosting and GitHub Pages

### What is Web Hosting?
- The process of making websites available on the internet
- Involves storing website files on a web server connected to the internet
- Allows anyone from anywhere to access the website 24/7

### Local Development vs Web Hosting
- Local development: Files are only available on your computer
- Web hosting: Files are available on a server connected to the internet

### Hosting with GitHub Pages

GitHub Pages is a free hosting service provided by GitHub. Here's how to use it:

1. Create a GitHub Account
   - Go to github.com
   - Sign up for a new account or sign in to an existing one

2. Create a New Repository
   - Click the '+' icon and select "New repository"
   - Name it (e.g., "html-portfolio")
   - Add a description (optional)
   - Set it to "Public"
   - Check "Add a README file"
   - Click "Create repository"

3. Upload Your Website Files
   - Click "Add file" > "Upload files"
   - Drag and drop your website files (not the folder, but its contents)
   - Ensure your main page is named "index.html"
   - Click "Commit changes"

4. Enable GitHub Pages
   - Go to "Settings" > "Pages"
   - Under "Branch", select "main" and the root folder
   - Click "Save"

5. Access Your Live Website
   - Wait for GitHub to process your site (can take 1-10 minutes)
   - Refresh the Pages settings page until you see a "Your site is live at" message
   - Click the provided link to view your live website

### Best Practices
- Always use "index.html" as your home page filename
- Double-check that all files and folders are uploaded correctly
- Be patient, as GitHub Pages can take a few minutes to update
- If you encounter errors, try refreshing or waiting a bit before trying again