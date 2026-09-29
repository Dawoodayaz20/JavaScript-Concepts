Closures in JavaScript:

> Closure is function remembering its lexical env after outer dies, causes stale state in React if dep array is wrong

> A **closure** is the combination of a function bundled together (enclosed) with references to its surrounding state (the **lexical environment**). In other words, a closure gives a function access to its outer scope.

> In simple words, A closure = A function that remembers the variables from where it was BORN, even after that place has finished.

```javascript
function outer() {
  let count = 0 // dies after outer() ends, right? NO.

  function inner() {
    count++ // inner still has access to it
    console.log(count)
  }
  return inner
}

const counter = outer() // outer() is DONE
counter() // 1 - but count still lives
counter() // 2 - it remembered
```

`count` should be garbage collected, but it's not. Because `inner` closed over it. That's closure.

##### Interview-level definition:

> When a function is returned from another function, it keeps a reference to its Lexical Environment. That Lexical Environment + function = Closure. 

> - Lexical Scoping = where variables ARE available (at write time).

> - Closure = what happens when a function KEEPS those variables alive after.

## Memory leaks in Closures:

A closure is created when an inner function maintains a reference to its outer (lexical) scope, even after the outer function has finished executing. Closures can cause memory leaks because in some scenarios, an outer function creates a big data object. After that outer function stops running, that data should be deleted from memory but if it has an inner funct() using that data, it keeps a reference to that object alive and the garbage collector is unable to remove it from the memory. Also, at times, when closures are formed with funct() that are tied to an event listener, the closures are long-lived and causes memory leak.


