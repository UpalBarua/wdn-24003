# Class 03: Advanced JavaScript - Asynchronous Programming and Working with APIs

### 🚀 Taking JavaScript to the Next Level

1. **Understanding Asynchronous JavaScript**

   - **Synchronous vs Asynchronous**

     - **Synchronous Code:** Executes line by line; each line waits for the previous one to finish.
     - **Asynchronous Code:** Allows tasks to be executed concurrently, without waiting for previous tasks to complete.

     - **Example (Synchronous):**

       ```javascript
       console.log("Start");
       console.log("End");
       ```

     - **Example (Asynchronous):**

       ```javascript
       console.log("Start");

       setTimeout(function () {
         console.log("This runs later");
       }, 2000);

       console.log("End");
       ```

   - **Event Loop**

     - The mechanism that handles asynchronous operations in JavaScript.
     - **How it works:** Callbacks are moved to the task queue and executed when the call stack is empty.

     - **Example:**

       ```javascript
       console.log("Start");

       setTimeout(function () {
         console.log("This runs last");
       }, 0);

       console.log("End");
       ```

2. **Promises: The Modern Approach to Asynchronous Programming**

   - **What is a Promise?**

     - An object that represents the eventual completion (or failure) of an asynchronous operation.
     - **States:** `Pending`, `Fulfilled`, `Rejected`.

     - **Example:**

       ```javascript
       let promise = new Promise(function (resolve, reject) {
         let success = true; // Change this to false to test rejection
         if (success) {
           resolve("Promise fulfilled!");
         } else {
           reject("Promise rejected!");
         }
       });

       promise
         .then(function (value) {
           console.log(value); // "Promise fulfilled!"
         })
         .catch(function (error) {
           console.log(error); // "Promise rejected!"
         });
       ```

   - **Chaining Promises**

     - Promises can be chained to handle multiple asynchronous operations sequentially.
     - **Example:**

       ```javascript
       let promise = new Promise(function (resolve) {
         resolve(1);
       });

       promise
         .then(function (value) {
           console.log(value); // 1
           return value * 2;
         })
         .then(function (value) {
           console.log(value); // 2
           return value * 3;
         })
         .then(function (value) {
           console.log(value); // 6
         });
       ```

   - **`Promise.all` and `Promise.race`**

     - **`Promise.all`**: Waits for all promises to be fulfilled.
     - **`Promise.race`**: Returns the result of the first settled promise.
     - **Example:**

       ```javascript
       let promise1 = new Promise((resolve) => setTimeout(resolve, 100, "One"));
       let promise2 = new Promise((resolve) => setTimeout(resolve, 200, "Two"));

       Promise.all([promise1, promise2]).then((values) => {
         console.log(values); // ["One", "Two"]
       });

       Promise.race([promise1, promise2]).then((value) => {
         console.log(value); // "One"
       });
       ```

3. **Async/Await: Syntactic Sugar for Promises**

   - **Introduction to `async` and `await`**

     - `async` functions always return a promise.
     - `await` pauses the execution of an `async` function until the promise is settled.

     - **Example:**

       ```javascript
       async function fetchData() {
         let response = await fetch(
           "https://jsonplaceholder.typicode.com/posts/1",
         );
         let data = await response.json();
         console.log(data);
       }

       fetchData();
       ```

   - **Error Handling with `try...catch`**

     - Errors in `async` functions can be handled using `try...catch`.
     - **Example:**

       ```javascript
       async function fetchData() {
         try {
           let response = await fetch(
             "https://jsonplaceholder.typicode.com/invalid-url",
           );
           let data = await response.json();
           console.log(data);
         } catch (error) {
           console.log("Error:", error);
         }
       }

       fetchData();
       ```

4. **Working with APIs**

   - **What is an API?**

     - Application Programming Interface (API) allows different software systems to communicate with each other.
     - **Example:**
       ```javascript
       // Fetching data from a public API
       fetch("https://jsonplaceholder.typicode.com/posts")
         .then((response) => response.json())
         .then((data) => console.log(data))
         .catch((error) => console.error("Error:", error));
       ```

   - **Making HTTP Requests with `fetch`**

     - **`fetch`** is a built-in JavaScript function for making network requests.
     - **Example (GET Request):**

       ```javascript
       fetch("https://jsonplaceholder.typicode.com/posts")
         .then((response) => response.json())
         .then((data) => console.log(data))
         .catch((error) => console.error("Error:", error));
       ```

     - **Example (POST Request):**
       ```javascript
       fetch("https://jsonplaceholder.typicode.com/posts", {
         method: "POST",
         body: JSON.stringify({
           title: "foo",
           body: "bar",
           userId: 1,
         }),
         headers: {
           "Content-type": "application/json; charset=UTF-8",
         },
       })
         .then((response) => response.json())
         .then((data) => console.log(data))
         .catch((error) => console.error("Error:", error));
       ```

5. **Practical Exercise: Building a Simple Weather App**

   - **Project Overview**

     - Build a small application that fetches weather data based on a city name input by the user.
     - **Steps:**
       1. Set up an HTML form with an input field for the city name.
       2. Use the `fetch` API to retrieve weather data from a public API (e.g., OpenWeatherMap).
       3. Display the fetched data (e.g., temperature, weather conditions) on the page.

   - **Example Code:**

     ```javascript
     document
       .querySelector("form")
       .addEventListener("submit", function (event) {
         event.preventDefault();
         let city = document.querySelector("input").value;
         let apiKey = "your_api_key_here";
         fetch(
           `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`,
         )
           .then((response) => response.json())
           .then((data) => {
             document.querySelector(".weather-info").textContent =
               `Temperature: ${data.main.temp}°C, Weather: ${data.weather[0].description}`;
           })
           .catch((error) => console.error("Error:", error));
       });
     ```

   - **Testing and Debugging**
     - Test the application with different city names.
     - Handle errors gracefully, such as when the city name is invalid.

#### Extra Resources

- **JavaScript.info on Asynchronous Programming:** [Asynchronous Programming](https://javascript.info/async)
  - A comprehensive guide to understanding asynchronous programming in JavaScript.
- **Mozilla Developer Network (MDN) Fetch API:** [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
  - Detailed documentation and examples for using the Fetch API.
