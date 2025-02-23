# 01. JavaScript Fundamentals - Part 1



tags: #JavaScript #Fundamentals #Beginner

---

## **1. Hello World!**

Let's start with the most basic program in JavaScript — the "Hello, World!" program. This is typically used to check if everything is set up correctly.


```js
console.log("Hello, World!");
```

---

## **2. A Brief Introduction to JS**

JavaScript is a **high-level, interpreted programming language** that allows you to create dynamic content on web pages. It is an essential technology alongside HTML and CSS for building modern websites and web applications.

- Initially designed for client-side scripting, JavaScript is now also widely used for server-side development with Node.js.
- JavaScript is **event-driven**, **functional**, and **imperative**, making it very versatile and widely used.

---

## **3. Linking a JS File**

To link a JavaScript file to your HTML, you need to use the `<script>` tag.

```html
<script src="script.js"></script>
```

You can place the `<script>` tag either in the `<head>` section (for synchronous loading) or just before the closing `</body>` tag (for asynchronous loading).

---

## **4. Values and Variables**

In JavaScript, values are data that can be stored in variables.

### Declaring variables:

```js
let x = 5;
const y = 10;
var z = 15;
```

- `let` is used for variables that can be reassigned.
- `const` is for constants (values that cannot be reassigned).
- `var` is the old way of declaring variables (before ES6), which has function-scoped behavior.

---

## **5. Data Types**

JavaScript supports several types of data:

- **Primitive types**: String, Number, Boolean, Null, Undefined, Symbol, BigInt.
- **Non-primitive types**: Object, Array, Function, Date, etc.

---

## **6. let, const, and var**

These are the three ways to declare variables in JavaScript:

- `let`: Block-scoped, can be reassigned.
- `const`: Block-scoped, cannot be reassigned.
- `var`: Function-scoped, can be reassigned (used in older JavaScript versions).

### Example:

```js
let a = 10;
const b = 20;
var c = 30;
```

---

## **7. Basic Operators**

JavaScript provides various operators, including:

- **Arithmetic operators**: `+`, `-`, `*`, `/`, `%`
- **Comparison operators**: `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`
- **Logical operators**: `&&`, `||`, `!`

---

## **8. Operator Precedence**

JavaScript follows a specific order when evaluating operators:

1. Parentheses `()`
2. Exponentiation `**`
3. Multiplication, division, modulo `* / %`
4. Addition and subtraction `+ -`
5. Comparison operators `== === > < >= <=`
6. Logical NOT `!`
7. Logical AND `&&`
8. Logical OR `||`

---

## **9. String and Template Literals**

Strings are used to represent text in JavaScript. You can use either single quotes (`'`) or double quotes (`"`) to define strings.

```js
let str = "Hello, World!";
```

Template literals (introduced in ES6) allow for easier string interpolation:

```js
let name = "John";
let greeting = `Hello, ${name}!`;
console.log(greeting); // Output: Hello, John!
```

---

## **10. Taking Decisions: if / else Statements**

Conditional statements are used to perform different actions based on different conditions.

```js
let age = 18;
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}
```

---

## **11. Type Conversion and Coercion**

- **Type Conversion** is manually converting a value from one type to another.
- **Type Coercion** is automatic conversion of one type to another by JavaScript.

```js
let num = "5";
let result = num * 1; // Type coercion: string to number
```

---

## **12. Truthy and Falsy Values**

JavaScript has **truthy** and **falsy** values. Falsy values are considered false when evaluated in a boolean context.

**Falsy values**:
- `false`, `0`, `""`, `null`, `undefined`, `NaN`

**Truthy values** are everything else.

```js
let value = 0;
if (value) {
    console.log("Truthy");
} else {
    console.log("Falsy");
}
```

---

## **13. Equality Logic: === vs ==**

- `==`: Loose equality operator, compares values after type coercion.
- `===`: Strict equality operator, compares both value and type without coercion.

```js
0 == "0";  // true
0 === "0"; // false
```

---

## **14. Boolean Logics**

Boolean logic uses **true** and **false** values to make decisions. Common Boolean operations include AND (`&&`), OR (`||`), and NOT (`!`).

```js
let x = true;
let y = false;
console.log(x && y); // false
console.log(x || y); // true
```

---

## **15. Logical Operators**

Logical operators allow us to combine or invert Boolean expressions.

- `&&` (AND): True if both sides are true.
- `||` (OR): True if either side is true.
- `!` (NOT): Reverses the truth value.

---

## **16. The Switch Statements**

A `switch` statement evaluates an expression and executes the corresponding case block.

```js
let day = 3;
switch (day) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    default:
        console.log("Invalid day");
}
```

---

## **17. Statements and Expressions**

A **statement** performs an action (e.g., a variable declaration, a function call). An **expression** returns a value.

```js
let x = 5; // x is an expression, let is a statement
```

---

## **18. Ternary Operators**

The ternary operator is a shorthand for `if/else` statements.

```js
let age = 20;
let result = age >= 18 ? "Adult" : "Minor";
console.log(result); // Output: Adult
```

---

## **19. ES5, ES6, ES-Next**

- **ES5** (ECMAScript 5): The fifth edition of JavaScript, which introduced features like `strict mode`, `JSON`, and better support for arrays.
- **ES6** (ECMAScript 2015): Introduced significant changes like `let`, `const`, arrow functions, template literals, classes, modules, and more.
- **ES-Next**: Refers to the next versions of JavaScript, which are constantly evolving with new features.

---
