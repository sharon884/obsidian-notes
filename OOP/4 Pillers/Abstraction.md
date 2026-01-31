


What is Abstraction?
> **Abstraction means showing only what is necessary and hiding how it is done.**

In short:

> **WHAT the object does, not HOW it does it**



Why Abstraction exists

Abstraction solves:

- Too much complexity
    
- Tight coupling
    
- Dependency on internal logic
    
- Fear of change
    

It answers this question:

> “What should the user of this code know — and what should they NOT care about?”




## Real-world analogy 
### Driving a car

You use:

- Steering
    
- Accelerator
    
- Brake
    

You do NOT care about:

- Engine pistons
    
- Fuel injection
    
- Gear mechanism
    

You interact with an **abstraction** (controls), not implementation.



## How Abstraction is achieved in OOP

Abstraction is implemented using:

1. **Interfaces**
    
2. **Abstract Classes**
    

You already know interfaces — great.

---

## Abstraction using INTERFACE 

### Step 1: Define WHAT (not how)

`interface Notification {   send(message: string): void; }`

This says:

> “Any notification must be able to send a message.”

No logic. No details.

---



### Step 2: Classes define HOW



`class EmailNotification implements Notification {   

send(message: string) {   

console.log("Email:", message);   
} 
};




class SMSNotification implements Notification {   

send(message: string) { 

console.log("SMS:", message);  
} 

}`

Each class decides **how**.

---

### Step 3: Caller depends on abstraction

`function notify(n: Notification) {   n.send("Hello Champ!"); }`

Caller:

- Does NOT know Email
    
- Does NOT know SMS
    
- Only knows the **contract**
    

That is abstraction in action.

---

##  Abstraction using ABSTRACT CLASS 

### What is an abstract class?

> A class that cannot be instantiated and may contain abstract methods.

Example:

`abstract class Notification {   abstract send(message: string): void; }`

Child must implement `send()`.

---

##  Interface vs Abstract Class 

|Interface|Abstract Class|
|---|---|
|Only contract|Contract + optional logic|
|No implementation|Can have implementation|
|Multiple allowed|Single inheritance|
|Pure abstraction|Partial abstraction|

👉 For your notification app: **Interface is perfect**.

---

## Abstraction vs Encapsulation (VERY IMPORTANT DIFFERENCE)

|Encapsulation|Abstraction|
|---|---|
|Hides data|Hides complexity|
|Controls access|Controls exposure|
|Focus: protection|Focus: simplicity|

They are related but **not the same**.

---

## Interview-ready one-liner (use this)

> “Abstraction hides implementation details and exposes only essential behavior using interfaces or abstract classes.”