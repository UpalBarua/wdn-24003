# Class 03: Enhancing Web Pages with CSS3

### 🎨 Advanced CSS Concepts

1. **CSS Variables**

   - **Custom Properties for Reusability:**

     - Define variables using `--` prefix and use them with `var()`.
     - **Example:**

       ```css
       :root {
         --primary-color: #3498db;
         --padding-size: 10px;
       }

       .container {
         background-color: var(--primary-color);
         padding: var(--padding-size);
       }
       ```

2. **CSS Flexbox (Revisited)**

   - **Advanced Flexbox Techniques:**

     - **Flexbox Alignment:** `align-self` to individually align items.
     - **Flexbox Wrapping:** `flex-wrap` to handle overflow of flex items.
     - **Example:**

       ```css
       .container {
         display: flex;
         flex-wrap: wrap;
       }

       .item {
         flex: 1 1 200px;
         margin: 10px;
       }
       ```

3. **CSS Grid Layout**

   - **Two-Dimensional Layouts:**

     - **Grid Container:** Use `display: grid;` to define a grid.
     - **Grid Items:** Place and size items within the grid using properties like `grid-template-columns`, `grid-template-rows`, and `gap`.
     - **Example:**

       ```css
       .grid-container {
         display: grid;
         grid-template-columns: 1fr 2fr;
         grid-template-rows: auto;
         gap: 10px;
       }

       .grid-item {
         background-color: lightblue;
         padding: 20px;
         text-align: center;
       }
       ```

   - **Practical Usage:**
     - **Create a Simple Layout:**
       ```html
       <div class="grid-container">
         <div class="grid-item">Header</div>
         <div class="grid-item">Sidebar</div>
         <div class="grid-item">Main Content</div>
       </div>
       ```

4. **CSS Transitions and Transformations**

   - **Transitions:** Animate changes to CSS properties.

     - **Properties:** `transition-property`, `transition-duration`, `transition-timing-function`, `transition-delay`.
     - **Example:**

       ```css
       .box {
         width: 100px;
         height: 100px;
         background-color: red;
         transition: background-color 0.5s ease;
       }

       .box:hover {
         background-color: blue;
       }
       ```

   - **Transformations:** Modify the appearance of elements.
     - **Properties:** `transform`, `rotate()`, `scale()`, `translate()`, `skew()`.
     - **Example:**
       ```css
       .box {
         transform: rotate(45deg);
       }
       ```
