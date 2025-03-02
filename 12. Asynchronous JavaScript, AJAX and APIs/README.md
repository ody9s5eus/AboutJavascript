# Asynchronous JavaScript: Promises, Async / Await, and AJAX

tags: #JavaScript #Async #Promises #AJAX #ModernJS

---

## **Asynchronous JavaScript, AJAX, and APIs**
Understanding asynchronous JavaScript, API calls, and AJAX for handling background operations efficiently.

---

## **XMLHttpRequest: The Old Way**
Before `fetch`, `XMLHttpRequest` was used to make HTTP requests.

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onload = function () {
  if (xhr.status === 200) {
    console.log(JSON.parse(xhr.responseText));
  }
};
xhr.send();
```

---

## **How the Web Works: Request and Response**
When a request is sent, the server processes it and returns a response containing data or errors.

---

## **Callback Hell**
Nested callbacks make code hard to read and maintain.

```js
setTimeout(() => {
  console.log('Step 1');
  setTimeout(() => {
    console.log('Step 2');
    setTimeout(() => {
      console.log('Step 3');
    }, 1000);
  }, 1000);
}, 1000);
```

---

## **Promises and the Fetch API**
`fetch` provides a cleaner way to handle asynchronous operations.

```js
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

---

## **Handling Rejected Promises**
Using `.catch()` to handle errors properly.

```js
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) throw new Error('Request failed');
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

---

## **The Event Loop: Behind the Scenes**
Understanding how JavaScript handles asynchronous operations using the event loop.

```js
console.log('Start');
setTimeout(() => console.log('Timeout'), 0);
Promise.resolve().then(() => console.log('Promise'));
console.log('End');
```

**Output:**
```
Start
End
Promise
Timeout
```

---

## **Building a Simple Promise**
Creating and consuming a promise.

```js
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => resolve('Success!'), 2000);
});

myPromise.then(result => console.log(result));
```

---

## **Promisifying Callbacks**
Convert callback-based functions into promises.

```js
const wait = (seconds) => new Promise(resolve => setTimeout(resolve, seconds * 1000));
wait(2).then(() => console.log('Waited for 2 seconds'));
```

---

## **Async / Await: A Modern Approach**
Simplifies working with promises.

```js
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

---

## **Error Handling with Try ... Catch**
Handling errors in `async` functions.

```js
async function safeFetch(url) {
  try {
    let response = await fetch(url);
    if (!response.ok) throw new Error(`HTTP error! Status: ${response.status}`);
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Fetch error:', error);
  }
}

safeFetch('https://api.example.com/data');
```

---

## **Returning Values from Async Functions**
Async functions return a promise.

```js
async function getNumber() {
  return 42;
}
getNumber().then(num => console.log(num));
```

---

## **Running Promises in Parallel**
Using `Promise.all()` to execute multiple promises concurrently.

```js
const p1 = fetch('https://api.example.com/data1').then(res => res.json());
const p2 = fetch('https://api.example.com/data2').then(res => res.json());

Promise.all([p1, p2]).then(results => console.log(results));
```

---

## **Other Promise Combinators: race, allSettled, any**

### `Promise.race()` - Resolves/rejects with the first completed promise.

```js
Promise.race([p1, p2]).then(result => console.log(result));
```

### `Promise.allSettled()` - Returns results of all promises, regardless of success/failure.

```js
Promise.allSettled([p1, p2]).then(results => console.log(results));
```

### `Promise.any()` - Resolves with the first fulfilled promise.

```js
Promise.any([p1, p2]).then(result => console.log(result));
```

---

## **Summary**
Mastering asynchronous JavaScript is essential for handling API calls, concurrency, and background tasks effectively.
