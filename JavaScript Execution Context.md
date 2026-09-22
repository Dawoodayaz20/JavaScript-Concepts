### JavaScript Execution Context:

JavaScript has execution contexts. It has three contexts.

1. **Global Execution Context**: This context is the global environment of javascript. Any code that has to run, is put into `this` keyword. So whenever we use `this` keyword outside a function in our code, we will get `{}` which is the `window-object`. Global context is defined before running any JS code either for few lines or a full web app.  

2. **Functional Execution Context**: This context is the context of executing code containing only the inner functional scope. Anything outer that function is beyond its scope. Anytime a function runs, it creates a functional context inside the global context. So we have a container like box inside a big window. Anything inside this box will not be accessible outside but we can access variables from the outside global context. The `return` value of any function is what exits that **functional context box** to the **global execution context**.   

3. Eval Execution Context: 

#### Phases:

There are two types of phases: 

1. **Memory-Creation phase**: In this phase, the variables are defined. We will take a look at this code below and see the phases in which it executes.
   
   ```javascript
   let val1 = 10;
   let val2 = 5;
   function add(num1, num2){
       let total = num1 + num2;
       return total;
   }
   let result1 = add(val1, val2)
   
   ```
   
   In this Memory phase, all variables will get defined like:
   
   ```javascript
   val1 ->  undefined
   val2 ->  undefined
   add -> function definition
   total->  undefined
   result1->  undefined
   result2->  undefined
   ```
   
   

2. **Execution Phase**: 
   Here in this, the variables will be initialized and the functions will execute:
   
   ```javascript
   val1 = 10
   val2 = 5
   function add() -> new environment + Execution thread
   result1 = total = 15
   result = 15
   ```
   
   Everytime a function will run, it will have a new execution context box created for it, in which it run. But for every functional sandbox, the code will go through its two phases which are **Memory Phase** and **Execution Phase**. This will then again **redefine** and **re-initialize** variables inside this function-scope execution context i-e `num1`, `num2`, `total`.
   
   After this function gets executed, it will then `delete` this context. The value returned from this function will be handed over to the variable `result1`.
