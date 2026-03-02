## Definition

> Software entities should be open for extension but closed for modification.

- Open for extension → New behavior can be added.
    
- Closed for modification → Existing tested code should not be changed.
    

---

## 🔹 Core Idea

Instead of modifying existing code when requirements change:

✔ Add new classes  
✔ Use interfaces  
✔ Use polymorphism

Avoid:

❌ Growing if-else  
❌ Switch-case expansion  
❌ Editing stable production code

---

## 🔹 Problem OCP Solves

When we modify existing code:

- Risk of regression bugs
    
- Increased testing effort
    
- Reduced stability
    
- Tight coupling
    
- Code becomes harder to scale
    

OCP ensures:

- Stability of core logic
    
- Flexible system design
    
- Safe feature addition
    

---

## 🔹 Implementation Pattern

OCP is usually implemented using:

- Interfaces
    
- Abstract classes
    
- Polymorphism
    
- Strategy Pattern
    
- Dependency Injection
    

---

## 🔹 Example Pattern (Conceptual)

Instead of:

if (paymentType === "credit") { ... }  
else if (paymentType === "paypal") { ... }

Use:

interface PaymentMethod {  
   process(): void;  
}

Add new classes without modifying existing ones.

---

## 🔹 Trade-Off

OCP increases:

- Number of classes
    
- Abstractions
    
- Structural complexity
    

Use OCP when:

- System is expected to grow
    
- Behavior changes frequently
    
- Extensibility is required
    

Avoid over-engineering small, stable systems.

---

## 🔹 One-Line Mental Model

> Stable core, flexible extensions.

> The biggest benefit of OCP is that it allows us to add new functionality without modifying existing, tested code, which reduces the risk of introducing bugs and improves system stability.