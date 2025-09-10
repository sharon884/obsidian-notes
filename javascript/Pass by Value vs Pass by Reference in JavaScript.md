


**1. Pass by Value**

- When a variable is passed, its **actual value is copied** into the new variable (or function parameter).
    
- The two variables are **independent** — changing one does not affect the other.
    
- **In JS, primitives are always passed by value.**


**Pass by Reference** (general concept in other languages)

- A variable is passed by giving its **memory address (reference)**, not the actual value.
    
- Both variables point to the **same memory location**, so a change in one reflects in the other.
    

⚠️ **But in JavaScript, this doesn’t exist directly.**  
Even for objects, **JavaScript still uses pass by value** — but the _value_ being passed is the **reference (the address of the object in heap)**



### 🔑 Key Interview Line

“In JavaScript, everything is technically **pass by value**.  
For primitives, the actual value is copied.  
For objects/arrays/functions, the reference itself is copied by value — so both variables point to the same object in heap. That’s why modifying properties works, but reassigning inside a function does not affect the original.”


