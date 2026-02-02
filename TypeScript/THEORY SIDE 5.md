

## What does “Erased Types” mean in TypeScript?

**Erased types** means:

> **All TypeScript types are removed during compilation and do NOT exist at runtime.**

That includes:

- `interface`
    
- `type`
    
- `enum` (const enum fully erased)
    
- Generics
    
- Type annotations
    

⚠️ JavaScript **never sees TypeScript types**.

---

## Example: Interface Erasure

`interface User {   name: string;   age: number; }  const user: User = {   name: "Champ",   age: 25 };`

⬇️ After transpilation:

`const user = {   name: "Champ",   age: 25 };`

 The **`User` interface is completely gone**.

---

## Why Interfaces Don’t Exist at Runtime

Because:

- Browsers understand **only JavaScript**
    
- Interfaces are **compile-time contracts**
    
- They are used **only by the type checker**
    

---

## Proof

`interface User {   name: string; }  console.log(User); // ❌ Error`

Why?  
👉 `User` never existed in JavaScript.

---

## Types vs Values

|Category|Exists at Runtime?|
|---|---|
|Interface|❌ No|
|Type Alias|❌ No|
|Generics|❌ No|
|Classes|✅ Yes|
|Functions|✅ Yes|
|Objects|✅ Yes|

---

## Classes are Different 

`class Person {   name: string; }  const p = new Person(); console.log(p instanceof Person); // ✅ true`

Classes:

- Exist at runtime
    
- Can be checked using `instanceof`
    

Interfaces:

- **Cannot**
    

---

## Common Interview Trap

❌ Wrong:

`if (user instanceof User) {}`

✅ Correct alternatives:

`// 1. Property check if ("name" in user) {}  // 2. Custom type guard function isUser(obj: any): obj is User {   return obj && typeof obj.name === "string"; }`

---

## Why TypeScript is Designed This Way

Because:

- Zero runtime overhead
    
- Fully compatible with JavaScript
    
- No performance penalty
    
- Types = safety net, not runtime system
    

---

## One-Line Interview Answer 

> **TypeScript uses type erasure, meaning interfaces and types are removed during compilation and do not exist at runtime. They are used only for static type checking.**

---

## Ultra-Crisp Summary 

- Interfaces exist **only at compile time**
    
- JS runtime knows **nothing about types**
    
- Classes exist at runtime, interfaces don’t
    
- This is called **type erasure**