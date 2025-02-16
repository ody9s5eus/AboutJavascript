# 2.  JavaScript Fundamentals - Part 2



tags: #JavaScript #Fundamentals #Intermediate

---



## **1. Activating Strict Mode**

Strict mode in JavaScript helps catch common coding mistakes and prevents the use of unsafe features.

To activate strict mode, you can add `"use strict";` at the beginning of a script or a function:

```js
"use strict"; // Activate strict mode

let x = 10; // This will throw an error if 'x' was not declared
```

Strict mode helps you avoid errors like assigning values to undeclared variables.

---

## **2. Function**

Functions are blocks of reusable code that perform a specific task. They can accept parameters and return a result.

### Defining a function:

```js
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Alice"));
```

---

## **3. Function Declaration & Expression**

There are two main ways to define a function in JavaScript: **function declaration** and **function expression**.

### Function Declaration:

```js
function add(a, b) {
    return a + b;
}
```

### Function Expression:

```js
const subtract = function(a, b) {
    return a - b;
};
```

The function declaration is hoisted, meaning it can be called before it’s defined, whereas a function expression is not hoisted.

---

## **4. Reviewing Functions**

Functions can also be **anonymous** (without a name) and can be used as **callback functions**.

### Example of an anonymous function:

```js
setTimeout(function() {
    console.log("Hello after 1 second!");
}, 1000);
```

---

## **5. Introduction to Array**

Arrays in JavaScript are ordered collections of values, which can be of any type.

### Creating an array:

```js
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // Output: apple
```

---

## **6. Basic Array Operations**

Common operations on arrays include adding, removing, and accessing elements.

- **push()**: Adds an element to the end.
- **pop()**: Removes the last element.
- **shift()**: Removes the first element.
- **unshift()**: Adds an element to the beginning.

```js
let colors = ["red", "green"];
colors.push("blue"); // Adds blue to the end
console.log(colors); // Output: ["red", "green", "blue"]
```

---

## **7. Introduction to Object**

Objects are collections of properties, where each property is a key-value pair. Keys are strings, and values can be of any type.

### Creating an object:

```js
let car = {
    make: "Toyota",
    model: "Camry",
    year: 2020
};
console.log(car.make); // Output: Toyota
```

---

## **8. Dot vs Bracket Notation**

You can access object properties using **dot notation** or **bracket notation**.

### Dot notation:

```js
let person = { name: "John", age: 30 };
console.log(person.name); // Output: John
```

### Bracket notation:

```js
let person = { name: "John", age: 30 };
console.log(person["name"]); // Output: John
```

Bracket notation is useful when the property name is dynamic or not a valid identifier.

---

## **9. Object Methods**

An object can also have methods, which are functions assigned to properties.

```js
let dog = {
    name: "Buddy",
    bark: function() {
        console.log("Woof!");
    }
};
dog.bark(); // Output: Woof!
```

---

## **10. Iteration: The for Loop**

The `for` loop is used to iterate over a block of code a specific number of times.

### Basic syntax:

```js
for (let i = 0; i < 5; i++) {
    console.log(i); // Output: 0 1 2 3 4
}
```

---

## **11. Looping Arrays, Breaking, and Continuing**

Arrays can also be iterated using `for` loops. You can use `break` to exit the loop early and `continue` to skip the current iteration.

### Example:

```js
let nums = [1, 2, 3, 4, 5];
for (let i = 0; i < nums.length; i++) {
    if (nums[i] === 3) {
        continue; // Skip 3
    }
    console.log(nums[i]); // Output: 1 2 4 5
}
```

---

## **12. Looping Backward and Loops in Loops**

You can loop backward by starting from the last element and decreasing the index. Nested loops allow you to loop through arrays inside arrays.

### Example of backward loop:

```js
let numbers = [1, 2, 3, 4];
for (let i = numbers.length - 1; i >= 0; i--) {
    console.log(numbers[i]); // Output: 4 3 2 1
}
```

### Example of nested loops:

```js
let matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
for (let i = 0; i < matrix.length; i++) {
    for (let j = 0; j < matrix[i].length; j++) {
        console.log(matrix[i][j]);
    }
}
```

---

## **13. The while Loop**

The `while` loop executes a block of code as long as the condition is true.

```js
let counter = 0;
while (counter < 5) {
    console.log(counter);
    counter++; // Output: 0 1 2 3 4
}
```

---
