# 5. How JavaScript Works Behind the Scenes

## 🚀 An High-Level Overview of JavaScript
JavaScript is a **high-level, interpreted, and dynamically typed** language used primarily for web development. It is single-threaded, non-blocking, and supports asynchronous programming.

---

## ⚡ The JavaScript Runtime and Engine
JavaScript runs inside a **JavaScript Engine**, such as:
- **V8** (Chrome, Node.js)
- **SpiderMonkey** (Firefox)
- **JavaScriptCore** (Safari)

Each engine consists of:
- **Memory Heap**: Where objects and variables are stored.
- **Call Stack**: Keeps track of function calls.
- **Web APIs**: Browser-provided features (DOM, Timers, Fetch API).
- **Event Loop & Callback Queue**: Handles asynchronous operations.

---

## 🧠 Execution Context and Call Stack
JavaScript code executes inside an **Execution Context (EC)**.
1. **Global Execution Context (GEC)** – Created when the script first runs.
2. **Function Execution Context (FEC)** – Created for each function call.

The **Call Stack** is a LIFO (Last In, First Out) data structure where function calls are pushed and popped.

```js
function greet() {
  console.log("Hello");
}

greet(); // Call Stack: [greet] → pop → []
```

---

## 🌍 Scopes and Scope Chain
JavaScript uses **Lexical Scoping**, meaning a function can access variables from its parent scope.

- **Global Scope**: Accessible everywhere.
- **Function Scope**: Variables inside functions.
- **Block Scope**: `let` and `const` inside `{}`.

```js
let globalVar = "I'm global!";

function outer() {
  let outerVar = "I'm outer!";
  function inner() {
    console.log(globalVar, outerVar);
  }
  inner();
}

outer(); // ✅ Can access globalVar and outerVar
```

---

## 🏗️ Variable Environment: Hoisting and TDZ
**Hoisting**: JavaScript moves variable/function declarations to the top of the scope.

**Temporal Dead Zone (TDZ)**: `let` and `const` exist in the TDZ until they are initialized.

```js
console.log(x); // ❌ ReferenceError (TDZ)
let x = 10;
```

```js
console.log(y); // ✅ Undefined (Hoisted)
var y = 20;
```

---

## 🔄 The `this` Keyword
`this` refers to the object that calls the function.

- In the **global scope**, `this` is `window` (browser) or `global` (Node.js).
- Inside an **object method**, `this` refers to the object.
- Inside **a regular function**, `this` is `undefined` in strict mode.
- **Arrow functions** do not have their own `this`.

```js
const obj = {
  name: "JS",
  show: function () {
    console.log(this.name); // ✅ "JS"
  },
};

obj.show();
```

---

## 📌 Regular Function vs Arrow Function
Arrow functions **do not** have their own `this`, instead, they inherit `this` from the surrounding scope.

```js
const obj = {
  value: 42,
  regFunction: function () {
    console.log(this.value); // ✅ 42
  },
  arrowFunction: () => {
    console.log(this.value); // ❌ Undefined (no own `this`)
  },
};
```

---

## 🛠️ Memory Management: Primitives vs Objects
**Primitives** (`string`, `number`, `boolean`) are stored in the **stack** (copied by value).
**Objects** (`arrays`, `functions`) are stored in the **heap** (copied by reference).

```js
let x = 10;
let y = x;
y = 20;
console.log(x); // ✅ 10
console.log(y); // ✅ 20
```

```js
let obj1 = { name: "Alice" };
let obj2 = obj1;
obj2.name = "Bob";
console.log(obj1.name); // ✅ "Bob" (same reference)
```

---

## 🔁 Object Reference in Practice (Shallow & Deep Copy)
**Shallow Copy** (copies reference):
```js
let objA = { a: 1, b: { c: 2 } };
let objB = Object.assign({}, objA);
objB.b.c = 99;
console.log(objA.b.c); // ❌ 99 (mutated original)
```

**Deep Copy** (creates a true copy):
```js
let objC = JSON.parse(JSON.stringify(objA));
objC.b.c = 42;
console.log(objA.b.c); // ✅ 2 (not mutated)
```

---

## 🗑️ Memory Management: Garbage Collection
JavaScript uses **Garbage Collection (GC)** to free unused memory. 

- **Mark-and-Sweep Algorithm**: Removes objects no longer referenced.
- **Reference Counting**: If an object has no references, it's deleted.

```js
let obj = { name: "temp" };
obj = null; // GC will clean this up
```

---

This concludes an in-depth look at how JavaScript works behind the scenes. Understanding these concepts will help you write more efficient and optimized JavaScript! 🚀
