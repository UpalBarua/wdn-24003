# Class 02: React Components & State Management

### 🧩 React Components & Props

1. **Functional Components:**

   - **Definition:** Functional components are JavaScript functions that return React elements. They are simpler and use hooks for state and side effects.
   - **Example:**

     ```jsx
     import React from "react";

     function Greeting(props) {
       return <h1>Hello, {props.name}!</h1>;
     }

     export default Greeting;
     ```

2. **Passing Props to Components:**

   - **Definition:** Props are used to pass data from a parent component to a child component.
   - **Example:**

     ```jsx
     function Welcome({ name }) {
       return <h1>Welcome, {name}!</h1>;
     }

     function App() {
       return <Welcome name="React" />;
     }

     export default App;
     ```

3. **Default Props:**

   - **Definition:** Default values for props if none are provided.
   - **Example:**

     ```jsx
     function Welcome({ name = "Guest" }) {
       return <h1>Welcome, {name}!</h1>;
     }

     export default Welcome;
     ```

### 🧩 State Management with Hooks

1. **Introduction to Hooks:**

   - **Definition:** Hooks are functions that let you use state and other React features without writing a class.

2. **Using `useState`:**

   - **Purpose:** Manage state in functional components.
   - **Example:**

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

3. **Using `useEffect`:**

   - **Purpose:** Manage side effects, like data fetching, in functional components.
   - **Example:**

     ```jsx
     import React, { useEffect, useState } from "react";

     function FetchData() {
       const [data, setData] = useState(null);

       useEffect(() => {
         fetch("https://api.example.com/data")
           .then((response) => response.json())
           .then((data) => setData(data));
       }, []); // Empty dependency array means this runs once after the initial render

       return (
         <div>
           <h1>Data:</h1>
           <pre>{JSON.stringify(data, null, 2)}</pre>
         </div>
       );
     }

     export default FetchData;
     ```

### 🧩 Handling Events

1. **Event Handling in React:**

   - **Definition:** React events are synthetic events that wrap the native DOM events and have consistent behavior across different browsers.
   - **Example:**

     ```jsx
     import React, { useState } from "react";

     function EventExample() {
       const [message, setMessage] = useState("Click the button!");

       const handleClick = () => {
         setMessage("Button clicked!");
       };

       return (
         <div>
           <p>{message}</p>
           <button onClick={handleClick}>Click Me</button>
         </div>
       );
     }

     export default EventExample;
     ```

2. **Form Handling:**

   - **Definition:** Handling form inputs and submissions in React.
   - **Example:**

     ```jsx
     import React, { useState } from "react";

     function FormExample() {
       const [name, setName] = useState("");

       const handleSubmit = (event) => {
         event.preventDefault();
         alert("Submitted name: " + name);
       };

       return (
         <form onSubmit={handleSubmit}>
           <label>
             Name:
             <input
               type="text"
               value={name}
               onChange={(e) => setName(e.target.value)}
             />
           </label>
           <button type="submit">Submit</button>
         </form>
       );
     }

     export default FormExample;
     ```

### 🧩 Conditional Rendering

1. **Using Conditional Statements:**

   - **Definition:** Render components or elements based on certain conditions.
   - **Example:**

     ```jsx
     import React, { useState } from "react";

     function ConditionalRendering() {
       const [isLoggedIn, setIsLoggedIn] = useState(false);

       return (
         <div>
           {isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please log in.</h1>}
           <button onClick={() => setIsLoggedIn(!isLoggedIn)}>
             Toggle Login
           </button>
         </div>
       );
     }

     export default ConditionalRendering;
     ```

### 📚 Extra Resources

- **React Official Documentation:** [React Docs](https://reactjs.org/docs/getting-started.html)
  - Comprehensive guide on React components and hooks.
- **React Hooks Guide:** [React Hooks](https://reactjs.org/docs/hooks-intro.html)
  - Introduction and detailed explanation of React Hooks.
- **Event Handling in React:** [React Events](https://reactjs.org/docs/handling-events.html)
  - Guide on handling events and forms in React.
