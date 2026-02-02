

## What is Typing?

**Typing** means how a language handles the **type of a variable** (number, string, object, etc.).




## Static Typing

###  What it is

Types are checked **at compile time** (before the code runs).

`let age: number = 25; age = "twenty"; // ❌ Error (compile-time)`

###  Characteristics

- Types are known early
    
- Errors caught before execution
    
- Safer for large applications
    

###  Examples

- TypeScript
    
- Java
    
- C++
    
- C#
    

---

## Dynamic Typing

###  What it is

Types are checked **at runtime** (while the code is running).

`let age = 25; age = "twenty"; // ✅ Allowed`

### Characteristics

- Types can change anytime
    
- Errors appear during execution
    
- Faster to write, riskier to maintain
    

### Examples

- JavaScript
    
- Python
    
- Ruby
    
- PHP
    

---

## Key Differences (Interview Table)

| Feature          | Static Typing | Dynamic Typing        |
| ---------------- | ------------- | --------------------- |
| Type checking    | Compile time  | Runtime               |
| Type change      | ❌ Not allowed | ✅ Allowed             |
| Error detection  | Early         | Late                  |
| Code safety      | High          | Medium                |
| Speed of writing | Slower        | Faster                |
| Best for         | Large apps    | Small / rapid scripts |

---

## Real-World Analogy 

- **Static typing** → Airport security (strict checks before boarding ✈️)
    
- **Dynamic typing** → Open road trip (freedom, but more risk 🚗)
    

---

## Why TypeScript uses Static Typing?

Because it:

- Prevents runtime bugs
    
- Improves refactoring
    
- Makes large teams productive
    
- Improves editor support
    

---

## Trick Interview Question 

**Q:** Is TypeScript purely statically typed?

**A:** ❌ No  
TypeScript is **optionally statically typed**  
You can still write dynamic code if you want.

`let data: any = 10; data = "hello"; // Allowed`

---

## 1-Line Interview Answer 

> **Static typing checks types at compile time, reducing runtime errors, while dynamic typing checks types at runtime, offering flexibility but higher risk of bugs. TypeScript uses optional static typing, whereas JavaScript is dynamically typed.**