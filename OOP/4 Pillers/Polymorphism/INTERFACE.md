


What is  INTERFACE?

 **An interface is a contract that defines _what_ a class must do, not _how_ it does it.**

Think:

- Interface = **rules / promise**
    
- Class = **implementation**




Real-world analogy
### Charger socket

- Socket defines:
    
    - Shape
        
    - Voltage
        
- It does NOT define:
    
    - How phone works internally
        

Any phone that fits the socket **must follow the rules**.

That socket is an **interface**.



## Why do we need Interfaces? (real reason)

Interfaces help us:

- Enforce consistency
    
- Enable polymorphism
    
- Reduce coupling
    
- Work safely in teams
    
- Design flexible systems
    

This is **core to large applications**.

---


## Simple Interface example

`interface Notification {  

send(message: string): void; 

}`

This means:

> Any class that implements `Notification` MUST have `send()`

---

## Class implementing Interface

`class EmailNotification implements Notification {

send(message: string): void {  

console.log("Email:", message); 
}

}`

If you forget `send()`:  
❌ TypeScript gives an error.

That’s **contract enforcement**.

---

## Interface + Polymorphism (IMPORTANT)

`function notifyUser(notification: Notification) { 

notification.send("Hello Champ!"); 

}`

You can pass:

`notifyUser(new EmailNotification()); 

notifyUser(new SMSNotification());`

Same function → different behavior  
This is **polymorphism using interface**.



## Interface vs Class (basic difference)

|Interface|Class|
|---|---|
|Defines contract|Defines implementation|
|No logic|Has logic|
|No constructor|Has constructor|
|Multiple allowed|Single inheritance|



## Interface vs Abstract Class

|Interface|Abstract Class|
|---|---|
|No implementation|Can have implementation|
|Multiple allowed|Single|
|Pure contract|Partial contract|


## IMPORTANT rules about Interfaces

- Cannot create object from interface ❌
    
- Used as **type**
    
- Implemented by classes
    
- Supports polymorphism



## One-line rule to remember (VERY IMPORTANT)

> **Interface defines WHAT must be done, not HOW it is done.**



## Without interface vs With interface

### Without interface

- Caller decides behavior
    
- Lots of conditions
    
- Hard to extend
    
- Fragile code
    

### With interface

- Caller depends on contract
    
- No conditionals
    
- Easy extension
    
- Safe code



## Why classes alone are NOT enough

You might ask:

> “Why not just use a base class?”

Good question.

- Interface allows **multiple inheritance**
    
- Interface has **no implementation**
    
- Interface is **pure contract**
    
- Interface avoids forced coupling
    

In TypeScript, interface is the cleanest contract.





ONE sentence that explains interface perfectly

An interface allows different classes to be used interchangeably by enforcing a common contract.

