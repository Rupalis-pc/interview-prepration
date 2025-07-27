
# Interview Preparation

This repository contains useful resources to prepare for front-end and JavaScript interviews.

## Table of Contents

1. [for...of vs forEach](#forof-vs-foreach)  
2. [map, filter, reduce](#map-filter-reduce)  
3. [useRef](#useref)  
4. [useMemo vs useCallback](#usememo-vs-usecallback)  
5. [Object Prototype](#object-prototype)  
6. [setTimeout vs setInterval](#settimeout-vs-setinterval)  
7. [useEffect](#useeffect)  
8. [useState](#usestate)  
9. [useLocation](#uselocation)  
10. [useParams](#useparams)  

---

## for...of vs forEach

Comparison between `for...of` loop and `forEach` method in iterating over arrays and other iterable objects.

```js
const arr = [1, 2, 3, 4];

// for...of: works with any iterable, can use break/continue/return
for (const num of arr) {
  console.log(num); // 1, 2, 3, 4
  if (num === 2) break; // can exit early
}

// forEach: array method, cannot break/continue/return from outer function
arr.forEach(num => {
  console.log(num); // 1, 2, 3, 4
  // break/continue not allowed here
});
```

```js
// for...of can iterate over strings directly
const str = "hello";
for (const char of str) {
  console.log(char); // h, e, l, l, o
}

// forEach cannot be used directly on strings; convert to array first
Array.from(str).forEach(char => {
  console.log(char); // h, e, l, l, o
});
```

**Note:**
- `for...of` works directly with strings (and any iterable).
- To use `forEach` with a string, convert it to an array first (e.g., `Array.from(str)` or `str.split("")`).

**Key differences:**
- `for...of` is a language construct, works with any iterable, supports break/continue/return, and does not return a value.
- `forEach` is an array method, cannot be broken out of early, and always returns `undefined`.

---

## map, filter, reduce

Core array methods used for transforming (`map`), filtering (`filter`), and reducing (`reduce`) data in JavaScript.

```js
const arr = [1, 2, 3, 4];

// map: transforms each element, returns a new array
const doubled = arr.map(x => x * 2); // [2, 4, 6, 8]

// filter: selects elements based on a condition, returns a new array
const even = arr.filter(x => x % 2 === 0); // [2, 4]

// reduce: accumulates values, returns a single value
const sum = arr.reduce((acc, x) => acc + x, 0); // 10
```

**Return type difference:**
- `map` and `filter` always return a new array.
- `reduce` returns a single value (number, object, etc.), not an array.

---

## useRef
A React Hook that persists mutable values and references DOM elements without causing re-renders.

---

## useMemo vs useCallback
Hooks for memoizing values (`useMemo`) and functions (`useCallback`) to optimize performance and avoid unnecessary re-renders.

---

## Object Prototype
JavaScript's prototype system enables inheritance and sharing of properties and methods between objects.

---

## setTimeout vs setInterval
- **setTimeout** executes a function once after a specified delay.  
- **setInterval** repeatedly executes a function at specified intervals.  

**Key differences**:
- `setTimeout` is for one-time delayed execution.  
- `setInterval` is for recurring tasks (e.g., polling).  
- Both return a timer ID which can be cleared using `clearTimeout` or `clearInterval`.

---

## useEffect
A React Hook for side effects in functional components.

**Use cases**:
- Fetching data  
- Subscribing to events  
- Updating the DOM  

**Variants**:
- Run on every render:  
  ```js
  useEffect(() => {
    // runs on every render
  });
  ```
- Run only once (on mount):  
  ```js
  useEffect(() => {
    // runs once on mount
  }, []);
  ```
- Run on specific dependency change:  
  ```js
  useEffect(() => {
    // runs when `count` changes
  }, [count]);
  ```

---

## useState
A React Hook to add state to functional components.

```js
const [count, setCount] = useState(0);
```

---

## useLocation
A hook from `react-router-dom` to get the current location object.

```js
import { useLocation } from 'react-router-dom';
const location = useLocation();
```

**Useful properties**:
- `location.pathname` – current path  
- `location.search` – query string  
- `location.state` – route state  

---

## useParams
A hook from `react-router-dom` to access URL parameters.

```js
import { useParams } from 'react-router-dom';
const { id } = useParams();
```

- Used for dynamic routes (e.g., `/user/:id`)  
- Returns an object of key-value pairs for each parameter

---
