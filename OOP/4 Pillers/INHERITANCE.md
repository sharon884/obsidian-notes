
## What is Inheritance? 

> **Inheritance allows a class (child) to reuse properties and methods of another class (parent).**


## Why do we need Inheritance? 

Inheritance helps to:

- Avoid code duplication
    
- Reuse common logic
    
- Represent real-world hierarchy
    
- Make code easier to extend


## Real-world analogy 
### Vehicle example

- Vehicle → speed, fuel, move()
    
- Car → inherits Vehicle
    
- Bike → inherits Vehicle
    

A **Car IS A Vehicle**  
A **Bike IS A Vehicle**

This **IS-A relationship** is the key idea.

## Simple code example (TypeScript-style)

`class Vehicle {  

move() {     console.log("Vehicle is moving");   }

} 

class Car extends Vehicle {   

honk() {     console.log("Car is honking");   } 

}`

What happens:

- `Car` automatically gets `move()`
    
- No need to rewrite it
    
- Car adds its own behavior

## Important rules of Inheritance

###  What child class can do

- Use parent methods
    
- Add new methods
    
- Override parent methods (later in polymorphism)
    

### ❌ What child class should NOT do

- Break parent behavior
    
- Change meaning of inherited methods





Inheritance vs Encapsulation

|Encapsulation|Inheritance|
|---|---|
|Protect data|Reuse behavior|
|Access control|Relationship|
|“Who can access?”|“Who is related?”|

They solve **different problems**.


## When to use Inheritance 

Use inheritance only when:

- There is a **clear IS-A relationship**
    
- Child truly represents a type of parent
    

### ❌ Bad example

- `User` → `AdminUser` (sometimes OK, sometimes not)
    
- `Car` → `Engine` ❌ (Car HAS an Engine)
    

That’s composition, not inheritance.

---

## Interview-ready one-liner

> “Inheritance allows a class to reuse and extend another class’s behavior using an IS-A relationship, reducing duplication.”



