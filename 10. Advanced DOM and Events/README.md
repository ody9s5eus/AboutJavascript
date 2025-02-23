# 10. Advanced DOM and Events

tags: #JavaScript #DOM #Events #ModernJS

---

## **How DOM Really Works**
The Document Object Model (DOM) represents the structure of a web page as a tree of nodes. Each HTML element is a node in this tree, which allows JavaScript to manipulate the page dynamically.

---

## **Selecting, Creating, and Deleting Elements**
JavaScript provides various methods to interact with DOM elements.

### **Selecting Elements**
```js
const header = document.querySelector('h1');
const allButtons = document.querySelectorAll('.btn');
```

### **Creating Elements**
```js
const newDiv = document.createElement('div');
newDiv.textContent = 'Hello, World!';
document.body.appendChild(newDiv);
```

### **Deleting Elements**
```js
const element = document.querySelector('.remove-me');
element.remove();
```

---

## **Styles, Attributes, and Classes**

### **Manipulating Styles**
```js
document.body.style.backgroundColor = 'lightblue';
```

### **Setting Attributes**
```js
const link = document.querySelector('a');
link.setAttribute('href', 'https://example.com');
```

### **Adding and Removing Classes**
```js
const box = document.querySelector('.box');
box.classList.add('hidden');
box.classList.remove('visible');
```

---

## **Implementing Smooth Scrolling**

```js
document.querySelector('.scroll-btn').addEventListener('click', function () {
  document.querySelector('#target-section').scrollIntoView({ behavior: 'smooth' });
});
```

---

## **Types of Events and Event Handlers**
JavaScript supports various events, such as `click`, `keydown`, `mouseover`, and more.

```js
document.addEventListener('keydown', function (event) {
  console.log(`Key pressed: ${event.key}`);
});
```

---

## **Event Propagation: Bubbling and Capturing**
Events travel through the DOM in two phases:
1. **Capturing phase** (top to bottom)
2. **Bubbling phase** (bottom to top)

```js
document.querySelector('.child').addEventListener('click', function () {
  console.log('Child clicked');
}, true); // Capturing phase

document.querySelector('.parent').addEventListener('click', function () {
  console.log('Parent clicked');
}); // Bubbling phase
```

---

## **Event Delegation: Implementing Page Navigation**

```js
document.querySelector('.nav').addEventListener('click', function (e) {
  if (e.target.classList.contains('nav-link')) {
    console.log(`Navigating to ${e.target.textContent}`);
  }
});
```

---

## **DOM Traversing**
Navigating through elements in the DOM.

```js
const element = document.querySelector('.child');
console.log(element.parentElement);
console.log(element.previousElementSibling);
console.log(element.nextElementSibling);
```

---

## **Building a Tabbed Component**

```js
document.querySelectorAll('.tab-btn').forEach(btn => {
  btn.addEventListener('click', function () {
    document.querySelectorAll('.tab-content').forEach(tc => tc.classList.remove('active'));
    document.querySelector(`#${this.dataset.tab}`).classList.add('active');
  });
});
```

---

## **Passing Arguments to Event Handlers**
Using an event listener with additional arguments.

```js
const showAlert = (message) => {
  return function () {
    alert(message);
  };
};

document.querySelector('.btn').addEventListener('click', showAlert('Button clicked!'));
```

---

## **Implementing a Sticky Navigation: The Scroll Event**

```js
window.addEventListener('scroll', function () {
  if (window.scrollY > 100) {
    document.querySelector('.nav').classList.add('sticky');
  } else {
    document.querySelector('.nav').classList.remove('sticky');
  }
});
```

---

## **A Better Way: The Intersection Observer API**

```js
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (!entry.isIntersecting) {
      document.querySelector('.nav').classList.add('sticky');
    } else {
      document.querySelector('.nav').classList.remove('sticky');
    }
  });
}, { root: null, threshold: 0 });

observer.observe(document.querySelector('.header'));
```

---

## **Revealing Elements on Scroll**

```js
const sections = document.querySelectorAll('.section');

const revealSection = (entries, observer) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      observer.unobserve(entry.target);
    }
  });
};

const sectionObserver = new IntersectionObserver(revealSection, { root: null, threshold: 0.1 });
sections.forEach(section => sectionObserver.observe(section));
```

---

## **Lazy Loading Images**

```js
const images = document.querySelectorAll('img[data-src]');

const loadImg = (entries, observer) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.src = entry.target.dataset.src;
      observer.unobserve(entry.target);
    }
  });
};

const imgObserver = new IntersectionObserver(loadImg, { root: null, threshold: 0.1 });
images.forEach(img => imgObserver.observe(img));
```

---

## **Building a Slider Component**

```js
let currentSlide = 0;
const slides = document.querySelectorAll('.slide');

document.querySelector('.next').addEventListener('click', function () {
  currentSlide = (currentSlide + 1) % slides.length;
  slides.forEach(s => s.classList.remove('active'));
  slides[currentSlide].classList.add('active');
});
```

---

## **Lifecycle DOM Events**
Events such as `DOMContentLoaded`, `load`, `beforeunload`, and `unload`.

```js
document.addEventListener('DOMContentLoaded', function () {
  console.log('Document fully loaded');
});
```

---

## **Efficient Script Loading: `defer` and `async`**
- `defer`: Loads scripts in order, after HTML parsing.
- `async`: Loads scripts as soon as they are available.

```html
<script defer src="script.js"></script>
<script async src="analytics.js"></script>
```
