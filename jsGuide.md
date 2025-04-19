# Most Asked JavaScript Interview Questions (with Code Examples and Explanations)

This comprehensive guide covers 50+ beginner to advanced JavaScript interview questions with clear explanations and practical code examples.

---


This guide covers beginner to advanced JavaScript interview questions with clear explanations and practical code examples.

---

## 1. What is the difference between `var`, `let`, and `const`?

### Explanation:
- `var`: Function-scoped, can be redeclared and updated. Hoisted with `undefined`.
- `let`: Block-scoped, cannot be redeclared in the same scope. Hoisted but not initialized.
- `const`: Block-scoped, cannot be redeclared or reassigned. Also hoisted but not initialized.

```javascript
var a = 1; // function scoped
let b = 2; // block scoped
const c = 3; // block scoped, constant
```

---

## 2. Explain closures in JavaScript

### Explanation:
A closure is when a function "remembers" the variables from its outer scope even after that outer function has finished executing.

```javascript
function outer() {
  let count = 0;
  return function inner() {
    count++;
    console.log(count);
  }
}

const counter = outer();
counter(); // 1
counter(); // 2
```

---

## 3. What is the event loop?

### Explanation:
The event loop handles asynchronous callbacks. JavaScript runs in a single-threaded environment, and the event loop helps manage tasks like `setTimeout`, `fetch`, and `promises` without blocking code execution.

```javascript
console.log("Start");
setTimeout(() => console.log("Timeout"), 0);
console.log("End");
// Output: Start, End, Timeout
```

---

## 4. Difference between `==` and `===`

### Explanation:
- `==`: Loose equality, performs type coercion.
- `===`: Strict equality, no type coercion.

```javascript
console.log(0 == '0');  // true
console.log(0 === '0'); // false
```

---

## 5. What is hoisting?

### Explanation:
Hoisting is JavaScript's default behavior of moving declarations to the top of the current scope.

```javascript
console.log(a); // undefined
var a = 5;
```

---

## 6. What is a Promise?

### Explanation:
A Promise represents a value which may be available now, or in the future, or never. It has three states: pending, resolved, rejected.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Done!"), 1000);
});

promise.then(result => console.log(result));
```

---

## 7. Explain async/await

### Explanation:
`async/await` is syntactic sugar over Promises, making asynchronous code look synchronous.

```javascript
async function fetchData() {
  const response = await fetch('https://api.example.com');
  const data = await response.json();
  console.log(data);
}
```

---

## 8. Difference between `null` and `undefined`

### Explanation:
- `undefined`: Variable is declared but not assigned.
- `null`: Intentional absence of value.

```javascript
let a;
console.log(a); // undefined
let b = null;
console.log(b); // null
```

---

## 9. What are arrow functions?

### Explanation:
Arrow functions provide a shorter syntax and lexically bind the `this` value.

```javascript
const add = (a, b) => a + b;
```

---

## 10. What is debounce and throttle?

### Explanation:
- **Debounce**: Delays execution until a pause.
- **Throttle**: Ensures execution at regular intervals.

```javascript
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}

function throttle(fn, limit) {
  let inThrottle;
  return function(...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => inThrottle = false, limit);
    }
  }
}
```

---

## 11. Difference between `map`, `filter`, and `reduce`

### Explanation:
- `map`: Transforms array elements.
- `filter`: Filters based on condition.
- `reduce`: Reduces array to a single value.

```javascript
const nums = [1, 2, 3, 4];
const squares = nums.map(n => n * n);
const evens = nums.filter(n => n % 2 === 0);
const sum = nums.reduce((acc, n) => acc + n, 0);
```

---

## 12. Explain prototypal inheritance

### Explanation:
Objects can inherit properties from other objects via the prototype chain.

```javascript
const person = {
  greet() { console.log("Hello"); }
};

const student = Object.create(person);
student.greet(); // Hello
```

---

## 13. What is a callback function?

### Explanation:
A callback is a function passed as an argument to another function.

```javascript
function greet(name, callback) {
  console.log("Hi " + name);
  callback();
}

greet("John", () => console.log("Callback executed"));
```

---

## 14. Difference between synchronous and asynchronous code

### Explanation:
- **Synchronous**: Code is executed line by line.
- **Asynchronous**: Code can run in the background and notify when done (e.g., via Promises or callbacks).

---

## 15. How does `this` work in JavaScript?

### Explanation:
`this` refers to the context in which a function is called. Arrow functions do not bind their own `this`.

```javascript
const obj = {
  value: 42,
  getValue() {
    return this.value;
  }
};

console.log(obj.getValue()); // 42
```

Arrow function example:
```javascript
const obj = {
  value: 42,
  getValue: () => this.value
};

console.log(obj.getValue()); // undefined (wrong context)
```

---

Let me know if you'd like to expand this with topics like event delegation, memory management, or modules!



---

## 16. What is the difference between `undefined` and `not defined`?

### Explanation:

- `undefined`: A variable has been declared but not assigned a value.
- `not defined`: A variable has not been declared at all and will throw a ReferenceError when accessed.

```javascript
let a;
console.log(a); // undefined
console.log(b); // ReferenceError: b is not defined
```

---

## 17. Explain the `typeof` operator

### Explanation:

Returns a string indicating the type of the unevaluated operand.

```javascript
console.log(typeof 42);        // 'number'
console.log(typeof 'hello');   // 'string'
console.log(typeof null);      // 'object'
console.log(typeof undefined); // 'undefined'
```

---

## 18. What is the difference between deep copy and shallow copy?

### Explanation:

- **Shallow copy**: Copies only the top-level references.
- **Deep copy**: Recursively copies all nested objects.

```javascript
let obj1 = { a: 1, b: { c: 2 } };
let shallow = { ...obj1 };
let deep = JSON.parse(JSON.stringify(obj1));
```

---

## 19. What is the `spread` operator?

### Explanation:

Used to expand or spread iterable objects.

```javascript
const arr = [1, 2];
const newArr = [...arr, 3, 4]; // [1, 2, 3, 4]
```

---

## 20. What is the difference between `call`, `apply`, and `bind`?

### Explanation:

- `call`: Invokes a function with a given `this` and arguments.
- `apply`: Same as `call`, but takes an array of arguments.
- `bind`: Returns a new function with bound `this`.

```javascript
function greet(greeting) {
  console.log(`${greeting}, ${this.name}`);
}
const person = { name: 'Alice' };
greet.call(person, 'Hello');
greet.apply(person, ['Hi']);
const bound = greet.bind(person);
bound('Hey');
```

---

## 21. What are template literals?

### Explanation:

Template literals allow embedded expressions using backticks (`` ` ``).

```javascript
let name = 'John';
console.log(`Hello, ${name}`);
```

---

## 22. What is destructuring?

### Explanation:

A way to unpack values from arrays or properties from objects.

```javascript
const [a, b] = [1, 2];
const { x, y } = { x: 10, y: 20 };
```

---

## 23. What are default parameters?

### Explanation:

Allows setting default values for function parameters.

```javascript
function greet(name = 'Guest') {
  console.log(`Hello, ${name}`);
}
```

---

## 24. What are rest parameters?

### Explanation:

Represents an indefinite number of arguments as an array.

```javascript
function sum(...nums) {
  return nums.reduce((a, b) => a + b);
}
```

---

## 25. What is the `Set` object?

### Explanation:

A collection of unique values.

```javascript
const s = new Set([1, 2, 2, 3]);
console.log(s); // Set(3) {1, 2, 3}
```

---

## 26. What is the `Map` object?

### Explanation:

A key-value pair collection with any data type as key.

```javascript
const m = new Map();
m.set('a', 1);
m.set(2, 'b');
```

---

## 27. What is the Temporal Dead Zone (TDZ)?

### Explanation:

The time between entering scope and being declared where `let` and `const` cannot be accessed.

```javascript
console.log(a); // ReferenceError
let a = 3;
```

---

## 28. What are Immediately Invoked Function Expressions (IIFE)?

### Explanation:

A function executed right after its definition.

```javascript
(function() {
  console.log('IIFE');
})();
```

---

## 29. What is memoization?

### Explanation:

Caching function results to avoid recomputation.

```javascript
function memoize(fn) {
  const cache = {};
  return function(n) {
    if (n in cache) return cache[n];
    return (cache[n] = fn(n));
  };
}
```

---

## 30. What is the use of `Object.freeze()`?

### Explanation:

Freezes an object so properties cannot be changed.

```javascript
const obj = Object.freeze({ a: 1 });
obj.a = 2; // ignored in strict mode
```

---

## 31. How to clone an object?

```javascript
const original = { a: 1 };
const clone1 = Object.assign({}, original);
const clone2 = { ...original };
```

---

## 32. What are higher-order functions?

### Explanation:

Functions that take other functions as arguments or return them.

```javascript
function greet(name) {
  return function(message) {
    return `${message}, ${name}`;
  }
}
```

---

## 33. What is the difference between `Array.from()` and `Array.of()`?

```javascript
Array.from('123'); // ['1','2','3']
Array.of(1, 2, 3);  // [1, 2, 3]
```

---

## 34. Explain the `instanceof` operator

### Explanation:

Checks if an object is an instance of a constructor.

```javascript
console.log([] instanceof Array); // true
```

---

## 35. What are modules in JavaScript?

### Explanation:

ES6 modules use `import` and `export` to share code.

```javascript
// utils.js
export const add = (a, b) => a + b;

// main.js
import { add } from './utils.js';
```

---

## 36. Difference between `Object.seal()` and `Object.freeze()`?

### Explanation:

- `seal`: Cannot add/remove properties, but values can be modified.
- `freeze`: Cannot add/remove/modify properties.

---

## 37. What is optional chaining `?.`?

### Explanation:

Safely access nested properties.

```javascript
const user = {};
console.log(user?.profile?.email); // undefined
```

---

## 38. What is the nullish coalescing operator `??`?

### Explanation:

Returns right-hand operand if left is `null` or `undefined`.

```javascript
let a = null;
console.log(a ?? 'default'); // default
```

---

## 39. How does garbage collection work in JavaScript?

### Explanation:

Uses reference counting and reachability to clean memory.

---

## 40. What are Web APIs?

### Explanation:

Browser-provided interfaces (like DOM, Fetch, Storage).

---

## 41. What is the DOM?

### Explanation:

Document Object Model is a tree representation of HTML.

---

## 42. Difference between `innerHTML`, `innerText`, and `textContent`

### Explanation:

- `innerHTML`: Includes HTML tags.
- `innerText`: Renders as visible text.
- `textContent`: Raw text, even hidden.

---

## 43. How to handle errors in JavaScript?

```javascript
try {
  throw new Error("Oops");
} catch (e) {
  console.log(e.message);
} finally {
  console.log("Always runs");
}
```

---

## 44. What is event delegation?

### Explanation:

Attach event listener to a parent to handle events from children.

---

## 45. What is the use of `async` without `await`?

### Explanation:

Returns a Promise regardless.

---

## 46. What is a microtask and macrotask queue?

### Explanation:

Microtasks (Promises) run before macrotasks (setTimeout).

---

## 47. What is a service worker?

### Explanation:

Script that runs in the background, enabling offline and caching.

---

## 48. What is a generator function?

```javascript
function* gen() {
  yield 1;
  yield 2;
}
const g = gen();
console.log(g.next());
```

---

## 49. What is a symbol in JavaScript?

### Explanation:

A unique and immutable primitive value used as object keys.

```javascript
const sym = Symbol('id');
```

---

## 50. What is currying?

### Explanation:

Transforms a function with multiple arguments into a sequence of functions.

```javascript
function curry(a) {
  return function(b) {
    return a + b;
  }
}
console.log(curry(5)(3));
```

---

Let me know if you'd like flashcards, quiz mode, or PDF formatting!

yes make it download pdf

