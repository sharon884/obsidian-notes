
- When we **create a function**, it gets its own **Lexical Environment**.
    
- The lexical environment contains:
    
    - The function’s **own local variables**
        
    - A **reference to its outer environment’s variables** (the outer function where it was created)
        
- So when **outer function finishes**, normally its variables are removed from memory.
    
- BUT — if an **inner function still exists and uses those variables**, JavaScript **keeps them alive in memory**.
    
- This behavior is called a **Closure**.
    
- Yes ✅ — closures happen **only with functions**, not with normal blocks or loops by themselves.


> “Closure is when after an outer function has finished, the inner function can still access the outer function’s variables because of lexical environment.”

---

## 💡 Why closures are useful (real use cases)

Closures are very useful when you want a function to **remember data between calls**, while **hiding it from outside code**.

---

### 🏦 Example 1 — Private variables (data privacy)

`function createAccount() {   let balance = 0; // private    return {     deposit(amount) {       balance += amount;     },     getBalance() {       return balance;     }   }; }  const account = createAccount(); account.deposit(100); console.log(account.getBalance()); // 100`

Here:

- `balance` is **hidden (private)** inside `createAccount`.
    
- Only the returned functions can access it (because of closure).
    

---

### 🧮 Example 2 — Counter that remembers the previous value

`function createCounter() {   let count = 0;    return function() {     count++;     console.log(count);   }; }  const counter = createCounter();  counter(); // 1 counter(); // 2 counter(); // 3`

Here:

- Each time `counter()` runs, it **remembers the old `count`**.
    
- This works only because `count` is preserved inside the closure.
    

---

### ⏳ Example 3 — Remembering values in callbacks

`function greetLater(name) {   setTimeout(function() {     console.log("Hello " + name);   }, 2000); }  greetLater("Sharon");`

Here:

- Even after `greetLater` finishes, the inner function inside `setTimeout` **still remembers `name`**.
    
- This is closure again!
    

---

## 📝 Summary

- Closure = inner function + remembered outer variables
    
- Happens because of lexical environment
    
- Only happens with functions
    
- Used for:
    
    - private variables
        
    - stateful logic (counters)
        
    - callbacks and async code

### Interview Answer

> A **Closure** in JavaScript is a feature where an **inner function remembers and can access variables from its outer function’s scope, even after the outer function has finished executing.**
> 
> This happens because of the **Lexical Environment**, which stores a reference to the outer scope variables when the function is created.
> 
> Closures are mainly used to **maintain private state, create data encapsulation, and preserve values across function calls**, especially in callbacks, event handlers, and modules.

