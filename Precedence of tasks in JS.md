## Precedence of tasks in JS:

JavaScript execution order follows a strict hierarchy:

1. **Synchronous Execution (Call Stack):** Top-level synchronous code executes immediately, line-by-line, until the Call Stack is completely empty.

2. **Microtasks Queue:** Once the synchronous stack clears, the event loop drains the entire microtask queue (e.g., `Promise.then()`, `queueMicrotask()`, `MutationObserver`, or `process.nextTick()` in Node.js).

3. **Macrotasks Queue:** Once all microtasks are finished, the event loop runs **one** macrotask (e.g., `setTimeout`, `setInterval`, `setImmediate`, I/O, UI events).

**Special Exceptions & Nuances**

* **In Node.js:** `process.nextTick()` callbacks run **before standard microtasks** (like Promise `.then()` callbacks). While both are microtasks, `nextTick` has its own high-priority queue that is drained before the general microtask queue.

* **In Browsers (Rendering):** `requestAnimationFrame` callbacks run _after_ microtasks finish but _before_ the browser repaints and runs the next macrotask.



```javascript
console.log("1: Synchronous");

setTimeout(() => {
  console.log("4: Macrotask");
}, 0);

Promise.resolve().then(() => {
  console.log("3: Microtask");
});

console.log("2: Synchronous");

// Execution Order:
// 1: Synchronous
// 2: Synchronous
// 3: Microtask
// 4: Macrotask
```


