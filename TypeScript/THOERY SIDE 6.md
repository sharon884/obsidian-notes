

<h1>Structural Typing</h1>
Structural typing means TypeScript checks whether an object has the required properties.  
If the required properties are missing, TypeScript throws a compile-time error.



## Why this is Structural Typing (not something else)

TypeScript **does NOT care about**:

- Object name
    
- Interface name
    
- Class name
    

It **ONLY cares about structure (shape)**:

- Required properties
    
- Required method signatures
    
- Their types




<h2> Correct Example</h2>

interface User {
  name: string;
  age: number;
}

const u1 = {
  name: "Champ",
  age: 25
};

const u2 = {
  name: "Champ"
};

let user: User;

user = u1; // ✅ OK (structure matches)

user = u2; // ❌ Error (age missing

❌ Error happens because:
👉 Required property is missing
👉 Structure does not match



## What Structural Typing is NOT 

It is **not**:

- Class-based typing
    
- Name-based typing (nominal typing)
    
- Runtime checking
    

---


## Duck Typing

> **Duck typing means: if an object has the required properties or methods, it is treated as that type — without caring about its actual type or class.**

In short:

- ❌ No type declaration required
    
- ❌ No interface required
    
- ✅ Only **properties/methods matter**
    
- ❗ Errors happen **at runtime**, not compile time
    

---
## Duck Typing Example (JavaScript)

`function greet(user) {  
console.log(user.name); }  

greet({ name: "Champ" });   // ✅ works

greet({ age: 25 });         // ❌ runtime error`

Here:

- JS does **not check beforehand**
    
- As long as `name` exists → works
    
- Missing property → crashes at runtime
    

This behavior is called **duck typing**.




## Key Difference (one table, done)

| Point            | Duck Typing | Structural Typing |
| ---------------- | ----------- | ----------------- |
| Language         | JavaScript  | TypeScript        |
| Checking time    | Runtime     | Compile time      |
| Interface needed | ❌ No        | ❌ No              |
| Safety           | Low         | High              |
| Error timing     | Late        | Early             |


## One-Line Interview Answer 

> **Duck typing checks object behavior at runtime, while structural typing checks object structure at compile time. TypeScript uses structural typing, which behaves like duck typing but is safer.**

---

## Ultra-Short Version

> **Duck typing = “it works if the property exists at runtime.”  
> Structural typing = “it must exist at compile time.”**



## One-Line Interview Answer 

> **Duck typing exists in JavaScript at runtime. TypeScript uses structural typing at compile time, which is inspired by duck typing but is not the same.**