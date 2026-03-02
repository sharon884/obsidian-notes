## 🔹 Definition

> Subtypes must be substitutable for their base types without altering the correctness of the program.

In simple terms:

> A child class should be able to replace its parent class without breaking expected behavior.

---

## 🔹 Core Idea

If `Child` extends `Parent`, then:

- Any code that works with `Parent`
    
- Should work correctly with `Child`
    
- Without unexpected errors
    
- Without changing expected output
    

LSP is about **behavioral compatibility**, not just inheritance syntax.

---

## 🔹 What LSP Protects

LSP ensures:

- Safe polymorphism
    
- Reliable inheritance
    
- No unexpected runtime failures
    
- Stable abstraction contracts
    

---

## 🔹 Behavioral Contract

When a parent class defines a method, it implicitly creates a **contract**:

- Expected input behavior (preconditions)
    
- Expected output behavior (postconditions)
    
- Expected guarantees
    

Child classes must:

✔ Not strengthen preconditions  
✔ Not weaken postconditions  
✔ Not throw unexpected errors  
✔ Not change logical meaning

---

## 🔹 Classic Violation Example (Rectangle–Square)

If:

class Rectangle {  
   setWidth(w: number) {}  
   setHeight(h: number) {}  
   getArea(): number {}  
}

And:

class Square extends Rectangle {  
   setWidth(w: number) {  
      this.width = w;  
      this.height = w;  
   }  
}

A function expecting Rectangle behavior may break when given Square.

This violates LSP because behavior changes.

---

## 🔹 Another Violation Example

class Bird {  
   fly() {}  
}  
  
class Penguin extends Bird {  
   fly() {  
      throw new Error("Cannot fly");  
   }  
}

Penguin breaks the expected behavior of Bird.

Wrong abstraction.

---

## 🔹 Correct Approach

Instead of forcing incorrect inheritance:

Use proper abstraction:

interface Bird {}  
  
interface FlyingBird extends Bird {  
   fly(): void;  
}

Design based on real behavior.

---

## 🔹 One-Line Mental Model

> If replacing a parent with a child changes expected behavior, LSP is violated.

---

## 🔹 Difference Between OCP and LSP

- **OCP** → Add new behavior without modifying existing code.
    
- **LSP** → Child classes must not break parent expectations.
    

OCP protects extension.  
LSP protects behavioral correctness.