# 04. JavaScript in the Browser: DOM and Events

## 📌 What is DOM and DOM Manipulation?
The **Document Object Model (DOM)** is a programming interface that represents an HTML document as a structured tree of elements. JavaScript allows us to manipulate this structure dynamically.

```js
console.log(document); // Outputs the entire DOM tree
console.log(document.documentElement); // Selects the root HTML element
console.log(document.body); // Selects the <body> element
```

---

## 📌 Selecting and Manipulating the DOM
We can select elements and modify their content or styles using JavaScript.

```js
// Selecting elements
const heading = document.querySelector("h1");
const allParagraphs = document.querySelectorAll("p");

// Changing text content
heading.textContent = "Hello, JavaScript DOM!";

// Changing styles
document.body.style.backgroundColor = "#f4f4f4";
```

---

## 📌 Handling Click Events
JavaScript enables interaction through **event listeners**.

```js
const button = document.querySelector(".btn");
button.addEventListener("click", function () {
  alert("Button Clicked!");
});
```

---

## 📌 Manipulating CSS Styles
You can dynamically modify CSS properties using JavaScript.

```js
const box = document.querySelector(".box");
box.style.width = "200px";
box.style.height = "200px";
box.style.backgroundColor = "blue";
```

---

## 📌 Handling Key Press Events
Listening for user keyboard interactions can improve UI experiences.

```js
document.addEventListener("keydown", function (event) {
  console.log(`Key pressed: ${event.key}`);
});
```

---

## 📌 Reading and Writing Persistent Data
Using **localStorage** and **sessionStorage**, we can store data in the browser.

```js
// Saving data
localStorage.setItem("username", "JohnDoe");

// Retrieving data
const user = localStorage.getItem("username");
console.log(user); // Outputs: JohnDoe

// Removing data
localStorage.removeItem("username");
```

With these concepts, you can build interactive web applications with JavaScript! 🚀
