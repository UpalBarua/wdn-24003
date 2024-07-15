# Class 02: Building on HTML & CSS Basics

### 🏗 Advanced HTML Concepts

1. **Tables**

   - **Basic Structure:** Organize data into rows and columns.
     - `<table>`: Defines a table.
     - `<tr>`: Defines a table row.
     - `<th>`: Defines a table header cell.
     - `<td>`: Defines a table data cell.
   - **Example:**
     ```html
     <table>
       <tr>
         <th>First Name</th>
         <th>Last Name</th>
       </tr>
       <tr>
         <td>John</td>
         <td>Doe</td>
       </tr>
       <tr>
         <td>Jane</td>
         <td>Smith</td>
       </tr>
     </table>
     ```

2. **Forms**

   - **Form Structure:** Collect user input.
     - `<form>`: Defines a form.
     - `<input>`: Defines an input field.
     - `<label>`: Defines a label for an input field.
     - `<textarea>`: Defines a multi-line text input.
     - `<button>`: Defines a clickable button.
     - `<select>`: Defines a drop-down list.
     - `<option>`: Defines an option in a drop-down list.
   - **Example:**
     ```html
     <form>
       <label for="fname">First Name:</label>
       <input type="text" id="fname" name="fname" />
       <br />
       <label for="lname">Last Name:</label>
       <input type="text" id="lname" name="lname" />
       <br />
       <input type="submit" value="Submit" />
     </form>
     ```

3. **Media Elements**

   - **Images:** Embedding and using responsive images.
     - `<img>`: Embeds an image.
     - `srcset` and `sizes`: Provide responsive images.
   - **Audio and Video:**
     - `<audio>`: Embeds audio content.
     - `<video>`: Embeds video content.
   - **Example:**
     ```html
     <img
       src="image.jpg"
       alt="Description"
       srcset="image-320w.jpg 320w, image-480w.jpg 480w, image-800w.jpg 800w"
       sizes="(max-width: 320px) 280px, (max-width: 480px) 440px, 800px"
     />
     <audio controls>
       <source src="audio.mp3" type="audio/mpeg" />
       Your browser does not support the audio element.
     </audio>
     <video width="320" height="240" controls>
       <source src="movie.mp4" type="video/mp4" />
       Your browser does not support the video tag.
     </video>
     ```

4. **Semantic HTML5 Elements**

   - **Purpose:** Improve the structure and accessibility of web pages.
   - **Common Semantic Elements:**
     - `<header>`: Defines a header for a document or section.
     - `<nav>`: Defines navigation links.
     - `<section>`: Defines a section in a document.
     - `<article>`: Defines an independent, self-contained content.
     - `<aside>`: Defines content aside from the main content.
     - `<footer>`: Defines a footer for a document or section.

### 🎨 Advanced CSS Concepts

1. **CSS Positioning**

   - **Static Positioning:** Default value; elements are positioned according to the normal flow of the document.
   - **Relative Positioning:** Positioned relative to its normal position.
   - **Absolute Positioning:** Positioned relative to the nearest positioned ancestor.
   - **Fixed Positioning:** Positioned relative to the viewport; does not move when scrolled.
   - **Sticky Positioning:** Positioned based on the user's scroll position.

   - **Example:**

     ```css
     .relative {
       position: relative;
       top: 10px;
       left: 20px;
     }

     .absolute {
       position: absolute;
       top: 50px;
       left: 100px;
     }

     .fixed {
       position: fixed;
       top: 0;
       right: 0;
     }

     .sticky {
       position: sticky;
       top: 0;
     }
     ```

2. **CSS Display Property**

   - **Purpose:** Specifies the display behavior of an element.
   - **Common Values:**
     - `block`: The element is displayed as a block-level element (e.g., `<div>`, `<p>`).
     - `inline`: The element is displayed as an inline-level element (e.g., `<span>`, `<a>`).
     - `inline-block`: The element is displayed as an inline-level block container.
     - `none`: The element is not displayed.
   - **Example:**

     ```css
     .block-element {
       display: block;
     }

     .inline-element {
       display: inline;
     }

     .inline-block-element {
       display: inline-block;
     }

     .hidden-element {
       display: none;
     }
     ```

3. **Flexbox**

   - **Purpose:** Provides a more efficient way to lay out, align, and distribute space among items in a container.
   - **Main Concepts:**
     - **Flex Container:** Parent element with `display: flex;`.
     - **Flex Items:** Direct children of the flex container.
   - **Flex Container Properties:**
     - `flex-direction`: Defines the direction of the flex items (row, column, row-reverse, column-reverse).
     - `justify-content`: Aligns flex items along the main axis (flex-start, flex-end, center, space-between, space-around).
     - `align-items`: Aligns flex items along the cross axis (flex-start, flex-end, center, baseline, stretch).
   - **Example:**

     ```css
     .container {
       display: flex;
       flex-direction: row;
       justify-content: space-between;
       align-items: center;
     }

     .item {
       flex: 1;
     }
     ```

4. **CSS Units**

   - **Absolute Units:**
     - `px` (pixels): Fixed size.
     - `cm` (centimeters): Fixed size.
     - `mm` (millimeters): Fixed size.
     - `in` (inches): Fixed size.
     - `pt` (points): 1/72 of an inch.
     - `pc` (picas): 1/6 of an inch.
   - **Relative Units:**
     - `%` (percentage): Relative to the parent element.
     - `em`: Relative to the font size of the element.
     - `rem`: Relative to the font size of the root element.
     - `vw` (viewport width): Relative to 1% of the viewport's width.
     - `vh` (viewport height): Relative to 1% of the viewport's height.
     - `vmin`: Relative to 1% of the viewport's smaller dimension.
     - `vmax`: Relative to 1% of the viewport's larger dimension.
   - **Example:**
     ```css
     .box {
       width: 50%;
       height: 100px;
       font-size: 2rem;
       margin: 10px;
       padding: 1em;
     }
     ```

5. **Images in CSS**

   - **Background Images:** Set an image as the background of an element.
     - `background-image`: Specifies the background image.
     - `background-repeat`: Controls the repetition of the background image.
     - `background-size`: Specifies the size of the background image.
     - `background-position`: Specifies the position of the background image.
   - **Example:**
     ```css
     .background {
       background-image: url("image.jpg");
       background-repeat: no-repeat;
       background-size: cover;
       background-position: center;
     }
     ```

6. **CSS Pseudo-classes**

   - **Purpose:** Style elements based on their state.
   - **Common Pseudo-classes:**
     - `:hover`: Applies when the user hovers over an element.
     - `:focus`: Applies when an element gains focus.
     - `:active`: Applies when an element is being activated by the user.
     - `:nth-child()`: Applies to elements based on their position in a group of siblings.
   - **Example:**

     ```css
     a:hover {
       color: red;
     }

     input:focus {
       border-color: blue;
     }

     button:active {
       background-color: green;
     }

     li:nth-child(odd) {
       background-color: lightgray;
     }

     li:nth-child(even) {
       background-color: white;
     }
     ```

#### Extra Resources

- **W3Schools HTML Tutorial:** [W3Schools HTML](https://www.w3schools.com/html/)
  - Comprehensive tutorial covering all HTML elements, attributes, and best practices.
- **Mozilla Developer Network (MDN) HTML Guide:** [MDN HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
  - Detailed documentation and examples of HTML concepts, elements, and attributes.
- **W3Schools CSS Tutorial:** [W3Schools CSS](https://www.w3schools.com/css/)
  - Comprehensive tutorial covering all CSS properties, selectors, and best practices.
- **Mozilla Developer Network (MDN) CSS Guide:** [MDN CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
  - Detailed documentation and examples of CSS concepts, properties, and selectors.
