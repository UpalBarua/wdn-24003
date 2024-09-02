# Class 01: Introduction to JavaScript

### 🌐 JavaScript Fundamentals

1. **Introduction to JavaScript**

   - **What is JavaScript?**

     - A programming language for the web.
     - Allows you to create dynamic and interactive web content.
     - Can be run on the client-side (in the browser) or server-side (with Node.js).

   - **Adding JavaScript to an HTML Page**

     - Inline: Using the `<script>` tag directly in HTML.
     - External: Linking a separate JavaScript file using the `<script src="script.js"></script>` tag.

     - **Example:**

       ```html
       <script>
         alert("Hello, World!");
       </script>
       ```

       ```html
       <script src="app.js"></script>
       ```

2. **Variables & Data Types**

   - **Declaring Variables**

     - `var`, `let`, `const`: The three ways to declare variables in JavaScript.
     - **`let` vs `const`**: `let` is for variables that can change, `const` is for variables that won’t change.

     - **Example:**
       ```javascript
       let name = "John";
       const age = 30;
       ```

   - **Data Types**

     - **Primitive Types:**
       - `String`: Textual data (e.g., `"Hello"`, `'World'`).
       - `Number`: Numeric data (e.g., `42`, `3.14`).
       - `Boolean`: Logical values (`true` or `false`).
       - `Null`: Represents the intentional absence of any object value.
       - `Undefined`: A variable that has been declared but not assigned a value.
       - `Symbol`: A unique and immutable primitive value.
     - **Complex Type:**

       - `Object`: Key-value pairs (e.g., `{ name: "John", age: 30 }`).

     - **Example:**
       ```javascript
       let message = "Hello, World!";
       let count = 42;
       let isActive = true;
       let user = { name: "Alice", age: 25 };
       ```

3. **Basic Operators**

   - **Arithmetic Operators**

     - `+`, `-`, `*`, `/`, `%`: Basic math operations.

   - **Comparison Operators**

     - `==`, `===`, `!=`, `!==`: Equality and inequality.
     - `<`, `>`, `<=`, `>=`: Greater than, less than, etc.

   - **Logical Operators**

     - `&&`: Logical AND.
     - `||`: Logical OR.
     - `!`: Logical NOT.

     - **Example:**
       ```javascript
       let a = 5;
       let b = 10;
       let sum = a + b; // 15
       let isEqual = a == b; // false
       let isGreater = a > b; // false
       let isActive = true && false; // false
       ```

4. **Control Flow**

   - **Conditional Statements**

     - `if`, `else if`, `else`: Execute code based on conditions.

     - **Example:**
       ```javascript
       let score = 85;
       if (score >= 90) {
         console.log("A");
       } else if (score >= 80) {
         console.log("B");
       } else {
         console.log("C");
       }
       ```

   - **Loops**

     - `for`, `while`, `do...while`: Repeat a block of code multiple times.

     - **Example:**

       ```javascript
       for (let i = 0; i < 5; i++) {
         console.log(i);
       }

       let count = 0;
       while (count < 5) {
         console.log(count);
         count++;
       }
       ```

5. **Functions**

   - **Declaring Functions**

     - Function declaration: Defines a function with the `function` keyword.
     - Function expression: Defines a function and assigns it to a variable.
     - Arrow function: A shorter syntax for writing function expressions.

     - **Example:**

       ```javascript
       function greet(name) {
         return "Hello, " + name;
       }

       const add = function (a, b) {
         return a + b;
       };

       const multiply = (a, b) => a * b;
       ```

   - **Parameters & Arguments**

     - Functions can accept parameters and return values.

     - **Example:**

       ```javascript
       function square(number) {
         return number * number;
       }

       let result = square(5); // 25
       ```

6. **Objects and Arrays**

   - **Objects**

     - Collections of related data and functions (methods).
     - **Accessing Properties**: Dot notation vs bracket notation.

     - **Example:**

       ```javascript
       let car = {
         make: "Toyota",
         model: "Corolla",
         year: 2020,
         drive: function () {
           console.log("Driving");
         },
       };

       console.log(car.make); // Toyota
       car.drive(); // Driving
       ```

   - **Arrays**

     - Ordered collections of values.
     - **Array Methods**: `push`, `pop`, `shift`, `unshift`, `length`.

     - **Example:**
       ```javascript
       let fruits = ["Apple", "Banana", "Orange"];
       fruits.push("Grape");
       console.log(fruits[0]); // Apple
       ```

7. **Introduction to the DOM (Document Object Model)**

   - **What is the DOM?**

     - A programming interface for web documents.
     - Represents the structure of a web page.
     - Allows JavaScript to interact with and manipulate HTML and CSS.

   - **Selecting Elements**

     - `getElementById`, `querySelector`, `querySelectorAll`.

     - **Example:**
       ```javascript
       let title = document.getElementById("title");
       let buttons = document.querySelectorAll(".btn");
       ```

   - **Manipulating Elements**

     - Changing text, HTML content, and attributes.

     - **Example:**
       ```javascript
       title.textContent = "Welcome!";
       title.style.color = "blue";
       ```

#### Extra Resources

- **JavaScript.info:** [JavaScript.info](https://javascript.info/)
  - Comprehensive guide covering all JavaScript concepts, from basics to advanced topics.
- **Mozilla Developer Network (MDN) JavaScript Guide:** [MDN JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
  - Detailed documentation and examples of JavaScript concepts, syntax, and best practices.
