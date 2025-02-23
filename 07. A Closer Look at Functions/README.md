# 07.  A Closer Look at Functions

tags: #JavaScript #Functions #ModernJS

---

## **Default Parameters**

JavaScript functions can have default parameter values.

```js

function greet(name = "Guest") {

console.log(`Hello, ${name}!`);

}

greet(); // Hello, Guest!

greet("Alice"); // Hello, Alice!

```

---

## **How Passing Arguments Works: Value vs References**

Primitive values are passed by value, objects and arrays by reference.

```js

let a = 10;

let b = a;

b = 20;

console.log(a, b); // 10, 20

  

let obj1 = { name: "Alice" };

let obj2 = obj1;

obj2.name = "Bob";

console.log(obj1.name); // Bob

```

---

## **First-Class and Higher-Order Functions**

Functions in JavaScript can be assigned to variables, passed as arguments, and returned from other functions.

```js

const add = (a, b) => a + b;

const operation = add;

console.log(operation(2, 3)); // 5

```

---

## **Function Accepting Callback Functions**

A function can receive another function as an argument.

```js

const processNumbers = (arr, callback) => arr.map(callback);

const squared = processNumbers([1, 2, 3], num => num * num);

console.log(squared); // [1, 4, 9]

```

---

## **Functions Returning Functions**

A function can return another function.


```js

const multiplier = factor => num => num * factor;

const double = multiplier(2);

console.log(double(5)); // 10

```

---

## **The Call and Apply Method**

Methods to explicitly set `this` in function execution.

```js

const person = { name: "Alice" };

function greet() {

console.log(`Hello, ${this.name}`);

}

greet.call(person);

```

---

## **Immediately Invoked Function Expression (IIFE)**

A function executed immediately after being defined.

```js

(function() {

console.log("Executed immediately!");

})();

```

---

## **Closures**

A closure allows a function to access variables from its outer scope even after the outer function has finished executing.

```js

function counter() {

let count = 0;

return function () {

count++;

console.log(count);

};

}

const increment = counter();

increment(); // 1

increment(); // 2

```

---

## **Closures Examples**

Closures are useful for encapsulation and maintaining state.

```js

function createUser(name) {

let score = 0;

return {

increment: () => score++,

getScore: () => console.log(`${name}'s score: ${score}`)

};

}

const user = createUser("Alice");

user.increment();

user.getScore(); // Alice's score: 1

```