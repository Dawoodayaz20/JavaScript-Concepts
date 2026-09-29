# `this` in JavaScript:

- The **`this`** keyword refers to the context where a piece of code, such as a function's body, is supposed to run. This context is different in every scenario like in Normal functions `function()`, Object methods `method: function(){}` and arrow functions `const method = () => {}`. 

## ## Normal functions:

- In Normal functions, when this is called, it references the global window object:
  
  ```javascript
  function getThis() {
    console.log(this);
  }
  
  //output: {} || global window object
  ```

### Object Methods:

- Mostly it is used in object methods. Like in here:

```javascript
const test = { 
    prop: 42, 
    func() { 
        return console.log(this.prop); 
    },
};
```

- here, `this` refers to the object that the method is attached to. 

- Normally, the value of `this` depends on how the function is invoked(runtime binding), not how it is defined. 

- Like the example you are seeing above, we have two scenarios:
  
  ```javascript
  // We can call it like:
  test.func();
  //console: 42
  
  // But if we call it a new instance:
  const testFunc = test.func();
  // Output: undefined || global Window object || {}
  ```

- An object methods doesn't remember the object it was written inside. It only looks at _who is invoking it right this second_. 

- Here is another example:
  
  ```javascript
  const user = {
    name: "Ali",
    greet: function() {
      console.log(this.name);
    }
  };
  
  // 1. Normal call
  user.greet(); 
  // Output: "Ali" 
  // (Why? Because 'user' is calling it directly to the left of the dot)
  
  // 2. The detached call
  const sayHello = user.greet;
  sayHello();
  // Output: undefined!
  ```

- Because even though it was *defined* inside 'user', it was *called* globally.

### Arrow Functions:

- Arrow functions do the exact opposite. They don't have their own `this` slot. Instead, they look at the surrounding scope _at the exact moment they are written_, and they **permanently lock it in**.
  
  ```javascript
  const user = {
    name: "Ali",
    // If we use an arrow function for a method:
    greet: () => {
      console.log(this.name);
    }
  };
  
  user.greet(); 
  // Output: undefined!
  ```

- Why? Because the arrow function looked *outside* the object when it was defined, where `this` was just the global Window object).

- It looks up for `this` in its lexical scope. Here, it tries to look up if there was any `this` when this object was defined, but at that time, it was only global object. 




