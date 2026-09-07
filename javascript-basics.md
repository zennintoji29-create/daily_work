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

---

### 📘 [Entry #4/31] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Understanding modern JS variable declarations, block scope vs function scope, and hoisting.

#### 💻 Code & Implementation
```javascript
// 1. const: Block-scoped, cannot be reassigned (Preferred default)
const PI = 3.14159;
// PI = 3.14; // TypeError: Assignment to constant variable

// 2. let: Block-scoped, can be reassigned
let score = 0;
score += 10;

// Block Scope Demonstration:
{
    let blockScoped = "I exist only inside this block {}";
    const alsoBlockScoped = "Me too";
    var functionScoped = "I leak outside normal blocks!";
}

// console.log(blockScoped); // ReferenceError: blockScoped is not defined
console.log(functionScoped); // Prints: "I leak outside normal blocks!"

// Best Practice Rule:
// Always use 'const' by default; use 'let' only when value must change. Avoid 'var'.
```

#### 🎯 Key Concepts & Takeaways
- `const` creates an immutable binding. Objects/arrays declared with `const` can still have their properties mutated.
- `let` is limited to the `{}` block in which it was defined, preventing accidental global leaks.
- `var` is hoisted and function-scoped, which often caused subtle bugs in older JavaScript codebases.

---

### 📘 [Entry #6/31] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
How inner functions remember variables from outer scopes and create private variables.

#### 💻 Code & Implementation
```javascript
// Factory function demonstrating Closure and Private State
function createCounter(initialValue = 0) {
    let count = initialValue; // Private variable, inaccessible from outside

    return {
        increment() {
            count++;
            return count;
        },
        decrement() {
            count--;
            return count;
        },
        getCount() {
            return count;
        }
    };
}

const counterA = createCounter(10);
console.log(counterA.increment()); // 11
console.log(counterA.increment()); // 12
console.log(counterA.getCount());  // 12
// counterA.count is undefined (encapsulation!)
```

#### 🎯 Key Concepts & Takeaways
- A closure is the combination of a function bundled together with references to its surrounding state (lexical environment).
- Closures give inner functions access to an outer function's scope even after the outer function has returned.
- Used for data encapsulation, function factories, and memoization.
