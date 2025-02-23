# 08. Working with Arrays

tags: #JavaScript #Arrays #ModernJS

---

## **Simple Array Methods**
Basic array methods like `push`, `pop`, `shift`, and `unshift`.

```js
let arr = [1, 2, 3];
arr.push(4); // [1, 2, 3, 4]
arr.pop(); // [1, 2, 3]
arr.shift(); // [2, 3]
arr.unshift(0); // [0, 2, 3]
```

---

## **New `at` Method**
Retrieves elements using positive or negative indexes.

```js
let numbers = [10, 20, 30, 40];
console.log(numbers.at(-1)); // 40
```

---

## **Looping Arrays: `forEach`**
Executes a function for each array element.

```js
let fruits = ["apple", "banana", "cherry"];
fruits.forEach(fruit => console.log(fruit));
```

---

## **`forEach` with Maps and Sets**

```js
let map = new Map([["a", 1], ["b", 2]]);
map.forEach((value, key) => console.log(key, value));
```

---

## **Data Transformations: `map`, `filter`, `reduce`**

### **The `map` Method**
Creates a new array with transformed elements.

```js
let nums = [1, 2, 3];
let doubled = nums.map(num => num * 2);
console.log(doubled); // [2, 4, 6]
```

### **The `filter` Method**
Filters elements based on a condition.

```js
let evenNumbers = nums.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2]
```

### **The `reduce` Method**
Reduces an array to a single value.

```js
let sum = nums.reduce((acc, num) => acc + num, 0);
console.log(sum); // 6
```

---

## **The Magic of Chaining Methods**
Combining methods for powerful transformations.

```js
let total = nums.filter(n => n > 1).map(n => n * 2).reduce((a, b) => a + b);
console.log(total); // 10
```

---

## **The `find` Method**
Finds the first element that matches a condition.

```js
let firstEven = nums.find(n => n % 2 === 0);
console.log(firstEven); // 2
```

## **The `findIndex` Method**
Returns the index of the first match.

```js
let index = nums.findIndex(n => n % 2 === 0);
console.log(index); // 1
```

---

## **The New `findLast` and `findLastIndex` Methods**
Finds elements from the end.

```js
let lastEven = nums.findLast(n => n % 2 === 0);
console.log(lastEven); // 2
```

---

## **Some and Every**
Checks conditions across elements.

```js
console.log(nums.some(n => n > 2)); // true
console.log(nums.every(n => n > 0)); // true
```

---

## **Flat and `flatMap`**
Flattens nested arrays.

```js
let nested = [[1, 2], [3, 4]];
console.log(nested.flat()); // [1, 2, 3, 4]
```

---

## **Sorting Arrays**
Sorting with `sort`.

```js
let letters = ["b", "a", "c"];
letters.sort();
console.log(letters); // ["a", "b", "c"]
```

---

## **Array Grouping**
Groups elements into an object.

```js
let people = [{ age: 20 }, { age: 30 }, { age: 20 }];
let grouped = people.reduce((acc, obj) => {
  (acc[obj.age] = acc[obj.age] || []).push(obj);
  return acc;
}, {});
console.log(grouped);
```

---

## **More Ways of Creating and Filling Arrays**

```js
console.log(Array.from({ length: 5 }, (_, i) => i));
```

---

## **Non-Destructive Alternatives: `toReversed`, `toSorted`, `toSpliced`, `with`**
Creates modified copies without mutating the original array.

```js
let original = [1, 2, 3];
let reversed = original.toReversed();
console.log(reversed); // [3, 2, 1]
```

---

## **When to Use Which Method**
Choosing the right array method based on use case.

---

## **Array Methods Practices**
Apply learned methods through hands-on exercises.
