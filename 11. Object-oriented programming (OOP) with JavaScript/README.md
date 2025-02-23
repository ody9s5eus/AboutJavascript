# 11. Object-oriented programming (OOP) with JavaScript

tags: #JavaScript #OOP #ModernJS

---

## **What is Object-oriented programming (OOP)?**
OOP is a programming paradigm based on the concept of objects, which can contain data (properties) and code (methods). It helps in structuring programs into reusable, modular components.

---

## **OOP in JavaScript**
JavaScript supports OOP through prototypal inheritance and ES6 classes.

---

## **Constructor Function and `new` Operator**
A constructor function is used to create objects.

```js
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const john = new Person('John', 30);
console.log(john);
```

---

## **Prototypes and Prototype Chain**
Every JavaScript object has a prototype from which it inherits properties and methods.

```js
Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

john.greet();
```

---

## **ES6 Classes**
ES6 introduced a cleaner syntax for OOP using `class`.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const alice = new Person('Alice', 25);
alice.greet();
```

---

## **Getters and Setters**
Encapsulate property access with `get` and `set`.

```js
class User {
  constructor(name) {
    this._name = name;
  }

  get name() {
    return this._name.toUpperCase();
  }

  set name(newName) {
    this._name = newName;
  }
}

const user = new User('David');
console.log(user.name); // DAVID
```

---

## **Static Methods**
Methods that belong to the class itself, not instances.

```js
class MathHelper {
  static add(a, b) {
    return a + b;
  }
}

console.log(MathHelper.add(5, 3));
```

---

## **Inheritance in JavaScript**
Using `extends` for class-based inheritance.

```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  bark() {
    console.log('Woof!');
  }
}

const buddy = new Dog('Buddy', 'Labrador');
buddy.speak();
buddy.bark();
```

---

## **Encapsulation: Private Fields and Methods**
Use `#` for truly private fields.

```js
class BankAccount {
  #balance;

  constructor(initialBalance) {
    this.#balance = initialBalance;
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount(1000);
console.log(account.getBalance());
// console.log(account.#balance); // Error: Private field
```

---

## **Method Chaining**
Returning `this` allows method chaining.

```js
class Car {
  constructor(model) {
    this.model = model;
    this.speed = 0;
  }

  accelerate(amount) {
    this.speed += amount;
    return this;
  }

  brake(amount) {
    this.speed -= amount;
    return this;
  }
}

const myCar = new Car('BMW').accelerate(50).brake(20);
console.log(myCar.speed);
```

---

## **Summary**
JavaScript's OOP model is based on prototypal inheritance and ES6 classes, providing powerful tools for structuring applications in a reusable and maintainable way.

---
