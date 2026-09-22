Hoisting:
========

JavaScript **Hoisting** refers to the process whereby the interpreter appears to move the _declaration_ of functions, variables, classes, or imports to the top of their [scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope), prior to execution of the code.

There are 4 types of behaviours that may be regarded as hoisting:

1. Being able to use a variable's value in its scope before the line it is declared. ("Value hoisting")
2. Being able to reference a variable in its scope before the line it is declared, without throwing a [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError), but the value is always [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined). ("Declaration hoisting")
3. The declaration of the variable causes behavior changes in its scope before the line in which it is declared.
4. The side effects of a declaration are produced before evaluating the rest of the code that contains it.

Here, `var` declaration is hoisted with type 2 behavior because it can be referenced before it is declared since it is moved to the top of the code on execution. 

While `let`, `const` and `Class` are hoisted with type 3 behavior.

### `var` vs `let`, `const` vs `function` hoisting:

`var`: You can refer to `var` declared variables anywhere in its scope even if its declaration isn't reached yet. However, when you access a variable before it's declared, the value is always `undefined`. 

`let` and `const`: Their's matter is in definition debate. Referencing the variable in the block before the variable declaration always results in a ReferenceError, because the variable is in a "[temporal dead zone](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#temporal_dead_zone_tdz)".

`function`: We will take a look at an example here:

```javascript
console.log(square(5)); // 25

function square(n) {
  return n * n;
}
```

This code runs without any error, because the JavaScript interpreter hoists the entire function declaration to the top of the current scope. 

But, if we declare a function like this:

```javascript
const square = function (n) {
  return n * n;
};
```

it will throw `ReferenceError: Cannot access 'square' before initialization`.

Function hoisting only works with function _declarations_ — not with function _expressions_.

> A **function declaration** defines a named function as a standalone statement using the `function` keyword.

> A **function expression** defines a function as part of a larger expression, typically by assigning it to a variable (`const`, `let`, or `var`).
