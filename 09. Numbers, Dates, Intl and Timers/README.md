# 09. Numbers, Dates, Intl and Timers

tags: #JavaScript #Numbers #Dates #Intl #Timers

---

## **Converting and Checking Numbers**
Understanding type conversion and checking numbers.

```js
console.log(Number("23")); // 23
console.log(+'23'); // 23
console.log(Number.isNaN(+'hello')); // true
console.log(Number.isFinite(10 / 0)); // false
```

---

## **Math and Rounding**
Using Math functions for calculations and rounding.

```js
console.log(Math.sqrt(25)); // 5
console.log(Math.max(1, 5, 3)); // 5
console.log(Math.round(4.6)); // 5
console.log(Math.trunc(4.9)); // 4
```

---

## **Numeric Separators**
Enhancing readability of large numbers.

```js
let largeNumber = 1_000_000;
console.log(largeNumber); // 1000000
```

---

## **Working with BigInt**
Handling large integers beyond `Number.MAX_SAFE_INTEGER`.

```js
let big = 9007199254740991n;
console.log(big + 1n); // 9007199254740992n
```

---

## **Creating Dates**
Working with JavaScript Date objects.

```js
let now = new Date();
console.log(now);
let specificDate = new Date(2023, 11, 24);
console.log(specificDate);
```

---

## **Operations with Dates**
Performing calculations on dates.

```js
let future = new Date(2025, 5, 1);
console.log(future.getFullYear());
console.log(future.getMonth());
console.log(future.getTime());
```

---

## **Internationalizing Dates (Intl)**
Formatting dates based on locale.

```js
let options = { year: 'numeric', month: 'long', day: 'numeric' };
console.log(new Intl.DateTimeFormat('en-US', options).format(new Date()));
```

---

## **Internationalizing Numbers (Intl)**
Formatting numbers based on locale.

```js
let number = 1234567.89;
console.log(new Intl.NumberFormat('de-DE').format(number)); // 1.234.567,89
```

---

## **Timers: `setTimeout`, `setInterval`**
Scheduling functions with timers.

```js
setTimeout(() => console.log('Hello after 3s'), 3000);
let interval = setInterval(() => console.log('Repeating every 2s'), 2000);
setTimeout(() => clearInterval(interval), 10000);
```
