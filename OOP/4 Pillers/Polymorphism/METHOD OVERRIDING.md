

What is Method Overriding?

> **Method overriding happens when a child class provides its own implementation of a method that already exists in the parent class.**

Key points:

- Same method name
    
- Same parameters
    
- Parent method is replaced **at runtime**




Why do we need Method Overriding?

Because:

- Different child objects behave differently
    
- Parent defines **what**
    
- Child defines **how**
    

Without overriding → polymorphism cannot exist.



### Parent

`class Notification { 

send() {  
console.log("Sending notification"); 
} 

};`

### Child overrides behavior

`class EmailNotification extends Notification {  

send() {   

console.log("Sending Email");  

}

};` 

Here:

- `send()` exists in parent
    
- Child **overrides** it
    
- Parent code is NOT changed





VERY IMPORTANT RULES

Method overriding requires:

1. Same method name
    
2. Same method signature
    
3. Parent method must be `public` or `protected`
    
4. Happens at **runtime**



## What overriding is NOT ❌

- ❌ Not changing method name
    
- ❌ Not adding extra parameters
    
- ❌ Not editing parent class code
    
- ❌ Not breaking encapsulation



## One-line interview answer

> “Method overriding allows a subclass to provide a specific implementation of a method already defined in its parent class, enabling polymorphism.”

