# 7. Data structures, Modern Operators and strings

tags: #JavaScript #DataStructures #ModernJS

---

## **Destructuring Arrays**
Destructuring allows extracting values from arrays and assigning them to variables.

```js
const numbers = [1, 2, 3];
const [a, b, c] = numbers;
console.log(a, b, c); // 1 2 3
```

---

## **Destructuring Objects**
You can also extract properties from objects and store them in variables.

```js
const person = { name: "Alice", age: 25 };
const { name, age } = person;
console.log(name, age); // Alice 25
```

---

## **The Spread Operator (`...`)**
The spread operator allows expanding elements of an array or object.

```js
const arr = [1, 2, 3];
const newArr = [...arr, 4, 5];
console.log(newArr); // [1, 2, 3, 4, 5]
```

---

## **The Rest Pattern and Parameters**
Rest syntax collects remaining elements into an array.

```js
const [first, ...rest] = [1, 2, 3, 4];
console.log(first, rest); // 1 [2, 3, 4]
```

---

## **Short Circuiting (`&&` and `||`)**
Logical operators return a value without evaluating both operands.

```js
console.log(0 || "Hello"); // Hello
console.log(1 && "World"); // World
```

---

## **The Nullish Coalescing Operator (`??`)**
It returns the right-hand value only if the left-hand value is `null` or `undefined`.

```js
let user;
console.log(user ?? "Guest"); // Guest
```

---

## **Logical Assignment Operators**
These combine assignment with logical operators.

```js
let a = null;
a ||= "default";
console.log(a); // default
```

---

## **Looping Arrays: The `for-of` Loop**
Iterate through array elements easily.

```js
const items = ["apple", "banana", "cherry"];
for (const item of items) {
  console.log(item);
}
```

---

## **Enhanced Object Literals**
Allows for more concise object creation.

```js
const age = 25;
const person = { name: "Alice", age };
console.log(person);
```

---

## **Optional Chaining (`?.`)**
Access nested object properties safely.

```js
const user = { profile: { name: "Alice" } };
console.log(user.profile?.name); // Alice
console.log(user.address?.street); // undefined
```

---

## **Looping Objects: Keys, Values, and Entries**

```js
const person = { name: "Alice", age: 25 };
for (const key in person) {
  console.log(`${key}: ${person[key]}`);
}
```

---

## **Sets**
A Set is a collection of unique values.

```js
const mySet = new Set([1, 2, 2, 3]);
console.log(mySet); // {1, 2, 3}
```

---

## **New Operations to Make Sets Useful**
Adding, deleting, and checking values in a Set.

```js
mySet.add(4);
console.log(mySet.has(4)); // true
mySet.delete(2);
console.log(mySet); // {1, 3, 4}
```

---

## **Maps Fundamentals**
A Map is a key-value pair collection with any type as a key.

```js
const myMap = new Map();
myMap.set("name", "Alice");
console.log(myMap.get("name")); // Alice
```

---

## **Maps: Iterations**

```js
myMap.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
```

---

## **When to Use Which Data Structure?**
- **Array**: Ordered collections.
- **Set**: Unique values.
- **Map**: Key-value storage.
- **Object**: Structured data.

---

## **Working with String Methods 1**

```js
let str = "JavaScript";
console.log(str.toUpperCase()); // JAVASCRIPT
```

---

## **Working with String Methods 2**

```js
console.log(str.includes("Script")); // true
```

---

## **Working with String Methods 3**

```js
console.log(str.replace("Java", "Type")); // TypeScript
```

---

## **String Methods in Practice**

```js
const sentence = "Hello JavaScript";
console.log(sentence.split(" ")); // ["Hello", "JavaScript"]
```

---

## **A Closer Look at Functions**

---

## **Default Parameters**
Set default values for function parameters.

```js
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}
greet(); // Hello, Guest!
```

---

## **How Passing Arguments Work: Value vs Reference**

```js
let num = 10;
function changeValue(x) {
  x = 20;
}
changeValue(num);
console.log(num); // 10 (unchanged)
```

---

## **First-Class and Higher-Order Functions**
Functions can be assigned to variables and passed as arguments.

```js
const add = (a, b) => a + b;
const operate = (fn, x, y) => fn(x, y);
console.log(operate(add, 5, 3)); // 8
```

---

## **The Call and Apply Methods**

```js
const person = { name: "Alice" };
function greet() {
  console.log(`Hello, ${this.name}!`);
}
greet.call(person); // Hello, Alice!
```

---

## **The Bind Method**
Creates a new function with `this` bound.

```js
const boundGreet = greet.bind(person);
boundGreet(); // Hello, Alice!
```

---

## **Immediately Invoked Function Expressions (IIFE)**

```js
(function () {
  console.log("This runs immediately");
})();
```

---

## **Closures**

```js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  };
}
const counter = outer();
counter(); // 1
counter(); // 2
```

---

This section provides an in-depth look at JavaScript functions! 🚀
