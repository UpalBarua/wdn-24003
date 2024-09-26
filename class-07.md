# Class 01: Introduction to React.js

### 🧩 What is React.js?

- **Definition:** React.js is a JavaScript library for building user interfaces, particularly single-page applications where you need a fast, interactive user experience.
- **Key Features:**
  - Component-based architecture
  - Virtual DOM for efficient updates
  - Declarative programming model

### 📦 Setting Up Your React Environment

1. **Create a React App with Vite:**

   - **Using Vite:** A modern build tool that provides a faster development experience.
     ```bash
     npm create vite@latest my-first-react-app --template react
     cd my-first-react-app
     npm install
     npm run dev
     ```
   - **Project Structure:**
     - `public/`: Contains static files.
     - `src/`: Contains JavaScript and CSS files.
     - `App.jsx`: Main component file.
     - `main.jsx`: Entry point of the application.

2. **Project Overview:**
   - **Run the App:** The default Vite setup includes a boilerplate React app which you can view in your browser at `http://localhost:5173`.
   - **Files to Note:**
     - `main.jsx`: Renders the root component into the DOM.
     - `App.jsx`: Contains the main app component.

### 🔍 Understanding React Components

1. **What is a Component?**

   - **Definition:** A component is a reusable piece of the UI that encapsulates its structure, style, and behavior.

2. **Creating a Functional Component:**

   - **Example:**

     ```jsx
     // src/App.jsx
     import React from "react";

     function App() {
       return (
         <div>
           <h1>Hello, React!</h1>
           <p>Welcome to your first React component.</p>
         </div>
       );
     }

     export default App;
     ```

3. **Rendering Components:**

   - **Entry Point:** `main.jsx` renders the root component.

     ```jsx
     // src/main.jsx
     import React from "react";
     import ReactDOM from "react-dom";
     import App from "./App";

     ReactDOM.render(
       <React.StrictMode>
         <App />
       </React.StrictMode>,
       document.getElementById("root"),
     );
     ```

### 🧩 JSX - JavaScript XML

1. **What is JSX?**

   - **Definition:** JSX is a syntax extension for JavaScript that allows you to write HTML-like code within JavaScript. It is transformed into JavaScript code by Babel.

2. **Basic JSX Syntax:**

   - **Example:**
     ```jsx
     const element = <h1>Hello, world!</h1>;
     ```

3. **Embedding Expressions:**

   - **Example:**
     ```jsx
     const name = "React";
     const element = <h1>Hello, {name}!</h1>;
     ```

4. **JSX Rules:**
   - **Use parentheses for multi-line JSX.**
   - **Only one root element per component.**
   - **Attributes are camelCase (e.g., `className` instead of `class`).**

### 🛠 Basic React Concepts

1. **Props:**

   - **Definition:** Props (short for properties) are used to pass data from parent components to child components.
   - **Example:**

     ```jsx
     function Welcome(props) {
       return <h1>Hello, {props.name}</h1>;
     }

     function App() {
       return <Welcome name="React" />;
     }
     ```

2. **State:**

   - **Definition:** State is used to manage data that changes over time within a component.
   - **Using State in Functional Components:**

     ```jsx
     import React, { useState } from "react";

     function Counter() {
       const [count, setCount] = useState(0);

       return (
         <div>
           <p>You clicked {count} times</p>
           <button onClick={() => setCount(count + 1)}>Click me</button>
         </div>
       );
     }

     export default Counter;
     ```

3. **Event Handling:**

   - **Handling Events in React:**

     ```jsx
     function handleClick() {
       alert("Button clicked!");
     }

     function App() {
       return <button onClick={handleClick}>Click me</button>;
     }
     ```

### 📚 Extra Resources

- **React Official Documentation:** [React Docs](https://reactjs.org/docs/getting-started.html)
  - Official guide and API documentation.
- **React Tutorial:** [React Tutorial](https://reactjs.org/tutorial/tutorial.html)
  - Interactive tutorial to build a tic-tac-toe game.
