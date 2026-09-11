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

---

### 📘 [Entry #13/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #20/31] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 7, 2026, 10:16 PM

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

### 📘 [Entry #31/31] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 7, 2026, 10:17 PM

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

### 📘 [Entry #2/35] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:26 AM

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

---

### 📘 [Entry #5/35] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:26 AM

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

### 📘 [Entry #12/35] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #19/35] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:27 AM

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

### 📘 [Entry #21/35] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:27 AM

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

### 📘 [Entry #23/35] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:27 AM

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

---

### 📘 [Entry #25/35] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #30/35] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 10:28 AM

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

---

### 📘 [Entry #9/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 09:12 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #10/31] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 09:12 PM

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

### 📘 [Entry #11/31] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 09:12 PM

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

### 📘 [Entry #18/31] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 09:13 PM

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

---

### 📘 [Entry #22/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #31/31] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 8, 2026, 09:14 PM

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

---

### 📘 [Entry #5/31] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:37 AM

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

---

### 📘 [Entry #15/31] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:37 AM

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

### 📘 [Entry #16/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:37 AM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #18/31] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:38 AM

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

### 📘 [Entry #26/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #28/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #29/31] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #4/30] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 10, 2026, 07:33 PM

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

### 📘 [Entry #5/30] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 10, 2026, 07:33 PM

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

---

### 📘 [Entry #10/30] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 10, 2026, 07:33 PM

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

### 📘 [Entry #12/30] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 10, 2026, 07:34 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #22/30] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 10, 2026, 07:34 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #24/30] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 10, 2026, 07:35 PM

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

### 📘 [Entry #1/27] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:57 PM

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

### 📘 [Entry #3/27] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:57 PM

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

---

### 📘 [Entry #7/27] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:57 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #15/27] JavaScript Basics: `let`, `const`, `var` & Scope
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:58 PM

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

### 📘 [Entry #21/27] JavaScript Promises, `async` / `await` & Fetch API
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:58 PM

#### 💡 Overview
Writing clean asynchronous code using Promises, `async`/`await`, and `try...catch` blocks.

#### 💻 Code & Implementation
```javascript
// Simulating an asynchronous database/network call
function fetchUserData(userId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (userId > 0) {
                resolve({ id: userId, name: "Subhansu", role: "Developer" });
            } else {
                reject(new Error("Invalid User ID"));
            }
        }, 500);
    });
}

// Modern async/await syntax:
async function displayUser(id) {
    try {
        console.log("Fetching user...");
        const user = await fetchUserData(id); // Pauses until Promise resolves
        console.log(`User Loaded: ${user.name} (${user.role})`);
    } catch (error) {
        console.error("Failed to load user:", error.message);
    } finally {
        console.log("Request completed.");
    }
}

displayUser(1);
```

#### 🎯 Key Concepts & Takeaways
- A `Promise` represents a value that may be available now, in the future, or never (Pending, Fulfilled, Rejected).
- `async` functions always return a Promise.
- `await` simplifies asynchronous control flow, eliminating callback hell.

---

### 📘 [Entry #22/27] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:58 PM

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

### 📘 [Entry #23/27] Essential Array Methods: `map()`, `filter()`, `reduce()`
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 07:59 PM

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

### 📘 [Entry #1/30] JavaScript Closures & Lexical Scoping
> **Track:** `JAVASCRIPT-BASICS` | **Updated:** Sep 11, 2026, 08:59 PM

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
