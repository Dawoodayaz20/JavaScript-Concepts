## Lexical Scoping:

The word _lexical_ refers to the fact that lexical scoping uses the location where a variable is declared. Nested functions have access to variables declared in their outer scope. For e.g

```javascript
function init() {
  var name = "Mozilla"; // name is a local variable created by init
  function displayName() {
    // displayName() is the inner function, that forms a closure
    console.log(name); // use variable declared in the parent function
  }
  displayName();
}
init();
```

Here, the console will log name defined in init function, which is the outer function. But the inner function has access to variables of the outer scope. 

#### Scoping with `var`, `let` and `const`:

JavaScript variables only had two kinds of scopes: function and global.

Variables declared with `var` are either function-scoped or global-scoped but it is tricky with declaring `var` as function scoped since the curly braces won't create scope. like for instance:

```javascript
if (Math.random() > 0.5) {
  var x = 1;
} else {
  var x = 2;
}
console.log(x);
```

Normally, you would think here, it will throw an error for logging `x` value, but that's not the case. Due to closure, `var` statements actually create global scope caring about no boundaries like the curly braces. 

This is why, using `var` has been so obsolete since it causes bugs due to its scope. 

#### `let` and `const`:

In ES6, JavaScript introduced the `let` and `const` declarations, which allow to define block-scoped variables. 

```javascript
function makeFunc() {
  const name = "Mozilla";
  function displayName() {
    console.log(name);
  }
  return displayName;
}

const myFunc = makeFunc();
myFunc();
```

Functions in JavaScript form closures. A _closure_ is the combination of a function and the lexical environment within which that function was declared. This environment consists of any variables that were in-scope at the time the closure was created. In this case, `myFunc` is a reference to the instance of the function `displayName` that is created when `makeFunc` is run.






















