### Call Stack in JavaScript:

**JavaScript Call Stack** is a fundamental mechanism that the JavaScript engine uses to keep track of function execution. the call stack is the tool the manages the single-line of execution synchronously. 

Think of it like a bucket, while going from top to bottom code statements, whenever a function gets called, the function is put into call stack. The function runs and is then removed from call stack. But sometimes, there are callback functions, in which we have called one function in another function. So, what happens, one function goes into the bucket, calls the next function, that function comes at the top of that function, gets executed and removed and then the function gets executed and removed after it. So this is why we say that call-stack works on LIFO (Last-in-First-Out) principle. 


