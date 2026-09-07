# 🌐 JavaScript & Modern Web Development Notes

> Beginner-friendly explanations of core JavaScript, ES6+ features, and asynchronous programming.


---

### 📘 [Entry #3/31] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Transforming, filtering, and aggregating arrays immutably with modern functional methods.

#### 💻 Code & Implementation
```javascript
const numbers = [1, 2, 3, 4, 5, 6];

// 1. map(): Transforms each element and returns a new array of the same length
const doubled = numbers.map(num => num * 2);
console.log("Doubled:", doubled); // [2, 4, 6, 8, 10, 12]

// 2. filter(): Returns a new array with elements that satisfy the condition
const evens = numbers.filter(num => num % 2 === 0);
console.log("Evens:", evens); // [2, 4, 6]

// 3. reduce(): Accumulates all elements into a single result (sum, object, tally)
const sum = numbers.reduce((accumulator, currentVal) => {
    return accumulator + currentVal;
}, 0); // 0 is initial accumulator value
console.log("Sum:", sum); // 21

// Chaining methods together:
const sumOfDoubledEvens = numbers
    .filter(n => n % 2 === 0)
    .map(n => n * 2)
    .reduce((acc, n) => acc + n, 0);
console.log("Chained result:", sumOfDoubledEvens); // (2*2) + (4*2) + (6*2) = 4 + 8 + 12 = 24
```

#### 🎯 Key Concepts & Takeaways
- `map()` produces a 1-to-1 transformation without modifying the original array.
- `filter()` keeps items where callback returns `true`.
- `reduce()` is the most versatile array method, capable of transforming arrays into objects, maps, or single values.
