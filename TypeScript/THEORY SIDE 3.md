
## Compilation

### What it is

**Compilation** is the process of converting **high-level source code into a lower-level language** (often machine code or bytecode).

`C / C++  →  Machine Code Java    →  Bytecode (.class)`

### Key Points

- Output is **not human-readable**
    
- Happens **before execution**
    
- Result runs **directly on machine / VM**
    

###  Examples

- C, C++
    
- Java
    
- Go
    

---

## Transpilation

###  What it is

**Transpilation** converts **source code to another source code** at the **same abstraction level**.

`TypeScript → JavaScript ES6       → ES5 JSX       → JavaScript`

### Key Points

- Output is **still readable code**
    
- Mainly for **compatibility**
    
- No direct machine code generation
    

### Examples

- TypeScript
    
- Babel
    
- JSX (React)
    

---

## JavaScript & TypeScript (Important Clarity)

- **JavaScript is NOT compiled** in the traditional sense
    
- **TypeScript is transpiled**, not compiled
    

Browser actually executes:

`TypeScript → JavaScript → Browser JS Engine → Machine Code`

---

## Side-by-Side Comparison 

| Feature         | Compilation             | Transpilation               |
| --------------- | ----------------------- | --------------------------- |
| Input           | High-level language     | High-level language         |
| Output          | Machine code / bytecode | Another high-level language |
| Readable output | ❌ No                    | ✅ Yes                       |
| Purpose         | Performance & execution | Compatibility & safety      |
| Example         | C → Machine code        | TS → JS                     |

---


---

## Interview Trick Question 

**Q:** Is TypeScript compiled or transpiled?

✅ **Correct Answer:**

> TypeScript is **transpiled** to JavaScript, then JavaScript is **compiled by the JS engine (JIT)** at runtime.


---




## 1-Line Interview Answer 

> **Compilation converts high-level code into machine-level code, whereas transpilation converts one high-level language into another. TypeScript is transpiled to JavaScript, not directly compiled to machine code.**

---



## Interview Gold Answer 

> **TypeScript reports compile-time errors because it performs static type checking during its compilation phase. Although it transpiles code to JavaScript, this compile phase happens before runtime and is independent of machine code generation.**