
> **JavaScript is a single-threaded language**, which means it runs one task at a time, line by line.  
> It runs inside a JavaScript engine such as the V8 engine (used by Google Chrome and Node.js).
> 
> Before any code runs, the engine creates a **Global Execution Context (GEC)**. Everything in JavaScript runs inside an **Execution Context**.  
> The GEC is also **pushed to the Call Stack**.
> 
> Each execution context has **two phases**:
> 
> 1. **Memory Creation Phase (Hoisting Phase)**
>     
> 
> - The code is scanned first.
>     
> - **`var`** variables are hoisted and initialized with `undefined`.
>     
> - **`let`** and **`const`** are hoisted but stay uninitialized inside the **Temporal Dead Zone (TDZ)** until their line is executed.
>     
> - **Function declarations** are hoisted with their full definitions.
>     
> 
> 2. **Execution Phase**
>     
> 
> - The code runs line by line.
>     
> - Values are assigned and functions are executed.
>     
> - When a function is called, a new **Function Execution Context (FEC)** is created and **pushed on top of the Call Stack**.
>     
> - After the function finishes, its context is **popped from the stack**, and control returns to the previous context (usually the GEC).
>     
> 
> After all synchronous code finishes and the **Call Stack becomes empty**, the **Event loop** starts checking the **Callback queue** and **Microtask queue** for any pending asynchronous tasks.  
> Those async tasks (like `setTimeout` or `fetch`) come from **Web APIs** provided by the Web browser and are pushed back to the **Call Stack** when ready.

✅ **This is the full lifecycle of JavaScript code execution.**


<h1> what is hoisting ?</h1>

## Interview-Ready Answer — What is Hoisting?

> **Hoisting is JavaScript’s default behavior of moving declarations to the top of their scope during the memory creation phase of execution.**
> 
> When the JavaScript engine starts running code, it first creates a **Execution context**.  
> In the **memory creation (hoisting) phase**, it scans through the code and allocates memory for all **variable and function declarations** before running any code line by line.
> 
> - **`var` declarations** are hoisted and automatically initialized with `undefined`.
>     
> - **`let` and `const` declarations** are also hoisted, but they are **not initialized**. They stay in the **Temporal Dead Zone (TDZ)** until the actual line of code is executed.
>     
> - **Function declarations** are hoisted with their **full function definitions**, so they can be called even before they appear in the code.
>     
> 
> Because of hoisting, you can use variables and functions **before their declaration line** — but only `var` and function declarations will work this way.  
> Trying to access `let` or `const` before their declaration will give a **ReferenceError**.

---

## ⚡ Quick Example

`console.log(a);   // undefined var a = 10;  sayHi();          // "Hello" function sayHi() {   console.log("Hello"); }  console.log(b);   // ReferenceError let b = 5;`

---

## 📝 Key Point

- Hoisting **only moves the declarations**, not the initializations (assignments).
    
- It happens **before execution begins**, during the creation phase of the execution context.

