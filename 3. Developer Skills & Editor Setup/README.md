# 3. Developer Skills & Editor Setup

tags: #JavaScript #DeveloperSkills #VSCode #Debugging  

---

## **1. Setting Up Prettier in VS Code**

Prettier is a code formatter that helps maintain a consistent code style.

### **📌 Steps to Install and Configure Prettier**
1. Open **VS Code** and go to the **Extensions Marketplace** (`Ctrl+Shift+X`).
2. Search for **Prettier - Code formatter** and install it.
3. Open the **settings.json** file (`Ctrl+Shift+P` → Search `Preferences: Open Settings (JSON)`).
4. Add the following configurations:



```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```

Now, Prettier will automatically format your code every time you save a file.

---

## **2. Installing Node.js & Setting Up Dev Environment**

Node.js allows you to run JavaScript outside the browser and is essential for backend development.

### **📌 Steps to Install Node.js**
1. Download Node.js from the [official website](https://nodejs.org/).
2. Install it and verify using the command:

```sh
node -v
```

1. Also, install **npm** (Node Package Manager) if it’s not included:

```sh
npm -v
```

2. (Optional) Install **nvm** (Node Version Manager) to manage multiple versions of Node.js:

```sh
nvm install 18
nvm use 18
```

---

## **3. Learning How to Code**

### **📌 Key Principles of Learning to Code**
- **Practice Daily**: Consistency is key.
- **Break Down Problems**: Solve smaller chunks first.
- **Read Documentation**: Use MDN, official docs, and guides.
- **Work on Projects**: Apply what you learn in real-world projects.

A great way to start is by following interactive coding tutorials like [freeCodeCamp](https://www.freecodecamp.org/) or [JavaScript.info](https://javascript.info/).

---

## **4. How to Think Like a Developer: Be a Problem Solver**

Programming is about **solving problems**. Here’s a step-by-step approach:

3. **Understand the Problem**: Read carefully and rephrase it in your own words.
4. **Break It Down**: Split the problem into smaller, manageable parts.
5. **Plan the Solution**: Write pseudocode before actual coding.
6. **Implement**: Start coding from the most fundamental part of the solution.
7. **Test & Debug**: Check for errors and unexpected behaviors.
8. **Refactor**: Improve and optimize your code for readability and performance.

**Example of Pseudocode**:

```plaintext
9. Get user input
10. Check if input is valid
11. Process the input
12. Return the result
```

Thinking in a structured way makes problem-solving easier.

---

## **5. Using Google, MDN, and Stack Overflow**

Every developer **Googles**. Here’s how to do it efficiently:

### **📌 How to Google Like a Developer**
- Be **specific**: Instead of searching *"fix error"*, try *"JavaScript TypeError: Cannot read property of undefined"*
- Use **error codes** from console logs.
- Include **relevant keywords** like *"JavaScript async/await issue"*
- Look for answers on **Stack Overflow**, **MDN Web Docs**, and **official documentation**.

### **📌 MDN Web Docs**
MDN Web Docs ([MDN](https://developer.mozilla.org/)) is the best resource for JavaScript and web development.

For example, to learn about `Array.map()`:

```sh
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
```

### **📌 Stack Overflow**
- Read **accepted answers** and **upvoted solutions**.
- If asking a question, provide a **clear problem statement** and **code examples**.

---

## **6. Debugging**

Debugging is the process of finding and fixing errors in your code.

### **📌 Common Debugging Steps**
13. **Read the error message carefully**.
14. **Reproduce the issue**: What causes it?
15. **Use `console.log()` to track values**.
16. **Check data types and logic errors**.
17. **Use breakpoints in DevTools** (Chrome/Firefox).

---

## **7. Debugging with Console & Breakpoints**

### **📌 Using `console.log()`**
One of the easiest ways to debug is by logging values to the console.

```js
let num = 10;
console.log("The value of num is:", num);
```

### **📌 Using `console.table()`**
If debugging arrays or objects:

```js
let users = [{ name: "Alice", age: 25 }, { name: "Bob", age: 30 }];
console.table(users);
```

### **📌 Using Breakpoints in DevTools**
18. Open **Developer Tools** (`F12` or `Ctrl+Shift+I` in Chrome).
19. Go to the **Sources** tab.
20. Click on a **line number** to set a breakpoint.
21. Refresh the page to pause execution at that line.

Breakpoints let you **step through** code and inspect variable values.

---
