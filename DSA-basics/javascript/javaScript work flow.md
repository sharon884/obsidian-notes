


## ⚙️ Step-by-Step — How JavaScript Works

### 1. 🧠 Single-Threaded

- JavaScript is **single-threaded**: it runs **one thing at a time**.
    
- It runs inside the V8 engine (used by Google Chrome and Node.js).
    

---

### 2. 🌍 Global Execution Context (GEC)

- **Created before any code runs.**
    
- Placed on the **Call Stack**.
    
- Has **two phases**:
    

---

### 3. 📦 Hoisting Phase (Memory Creation Phase)

- JS scans the entire file first and **allocates memory** for all declarations.
    
- **`var`**: hoisted and initialized with `undefined`.
    
- **`let` / `const`**: hoisted too, but left **uninitialized** in the **Temporal Dead Zone (TDZ)** until their line of code is reached.
    
- **Function declarations**: hoisted with their **full function definition**.
    

✅ This is called **Hoisting**.

---

### 4. ⚡ Execution Phase

- Code runs **line by line**.
    
- Variables are assigned values.
    
- Whenever a function is called:
    
    - A **Function Execution Context (FEC)** is created
        
    - That FEC is **pushed on top of the Call Stack**
        
- When the function finishes:
    
    - Its context is **popped from the Call Stack**
        
    - Control returns to the previous context (often the GEC)
        

---

### 5. 🔁 Event Loop and Async Tasks

- When the **Call Stack is empty**, the **Event loop** checks the:
    
    - **Callback queue**
        
    - **Microtask queue**
        
- It pushes the waiting asynchronous callbacks back into the **Call Stack**.
    
- These async tasks come from **Web APIs** (like `setTimeout`, `fetch`, etc.) which are handled by the Web browser.



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



