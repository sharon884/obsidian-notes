
## What is Declaration Merging?

👉 **Declaration merging means TypeScript automatically combines multiple declarations with the same name into a single definition.**

⚠️ This works with **interfaces**, **NOT with type aliases**.

---

## Basic Example

`interface User {   name: string; } 

interface User {   age: number; }`

TypeScript merges them into:

`interface User {   name: string;   age: number; }`

Now this is valid ✅

`const user: User = {   name: "Ace",   age: 25, };`

---

## Why does this exist?

Because:

- Large codebases
    
- Plugin-based architecture
    
- Library augmentation
    
- Extending third-party types safely
    

This is **huge** in real-world TS.


## Declaration Merging DOES NOT work with `type`

❌ This is illegal:

`type User = { name: string }; type User = { age: number }; // error`

👉 Types **cannot be re-opened**.



## Function Declaration Merging (advanced)

Interfaces can merge function signatures:

`interface Logger {   log(message: string): void; }  interface Logger {   log(error: Error): void; }`

Result:

`log(message: string): void; log(error: Error): void;`

This creates **function overloading**.

---

## Interview-ready definition 

> **Declaration merging is a TypeScript feature where multiple interface declarations with the same name are automatically combined into a single interface. This allows interfaces to be extended incrementally, unlike type aliases.**


