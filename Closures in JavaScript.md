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
