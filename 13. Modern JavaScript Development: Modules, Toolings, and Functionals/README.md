# Modern JavaScript Development: Modules, Toolings, and Functionals

tags: #JavaScript #Modules #Tooling #FunctionalProgramming #ModernJS

---

## **An Overview of Modern JavaScript Development**
Modern JavaScript development involves using modules, build tools, and functional programming concepts to create scalable applications efficiently.

---

## **An Overview of Modules in JavaScript**
Modules allow us to split code into separate files, improving maintainability and reusability.

---

## **Export and Importing in ES6 Modules**
ES6 introduced the `export` and `import` syntax for modular JavaScript.

```js
// exporting a function
export function greet(name) {
  return `Hello, ${name}!`;
}

// importing the function
import { greet } from './module.js';
console.log(greet('Alice'));
```

---

## **Top-Level Await (ES2022)**
Using `await` at the top level of a module.

```js
// top-level await
const data = await fetch('https://api.example.com/data').then(res => res.json());
console.log(data);
```

---

## **The Module Pattern**
A design pattern for structuring JavaScript code into self-contained modules.

```js
const CounterModule = (function () {
  let count = 0;
  return {
    increment: () => ++count,
    decrement: () => --count,
    getCount: () => count,
  };
})();
console.log(CounterModule.increment());
```

---

## **CommonJS Pattern**
Node.js uses CommonJS for module management.

```js
// exporting in CommonJS
module.exports = function greet(name) {
  return `Hello, ${name}!`;
};

// importing in CommonJS
const greet = require('./module');
console.log(greet('Alice'));
```

---

## **A Brief Introduction to the Command Line**
Developers use the command line to run scripts, manage dependencies, and automate tasks.

```sh
# Checking Node.js version
node -v
```

---

## **Introduction to NPM**
NPM (Node Package Manager) helps manage dependencies.

```sh
# Initialize a new package.json file
npm init -y
```

---

## **Building with Parcel and NPM Scripts**
Parcel simplifies bundling JavaScript projects.

```sh
# Install Parcel
npm install -g parcel-bundler

# Run a development server
parcel index.html
```

---

## **Configuring Babel and Polyfilling**
Babel transpiles modern JavaScript to support older browsers.

```sh
# Install Babel
npm install --save-dev @babel/core @babel/preset-env
```

---

## **Review: Writing Clean and Modern JavaScript**
Use best practices like `const`, `let`, arrow functions, and template literals.

```js
const greet = (name) => `Hello, ${name}!`;
console.log(greet('Alice'));
```

---

## **Declarative and Functional JavaScript Principles**
Using functional programming concepts like immutability and pure functions.

```js
const double = (arr) => arr.map(num => num * 2);
console.log(double([1, 2, 3]));
```

---

## **Summary**
Modern JavaScript development leverages modules, build tools, and functional programming for efficient and scalable applications.
