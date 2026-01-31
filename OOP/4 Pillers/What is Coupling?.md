
## What is Coupling? 

> **Coupling describes how much one piece of code depends on another piece of code.**

- High dependency → **tight coupling**
    
- Low dependency → **loose coupling**


## Tight Coupling (problematic)

### Meaning

> When one class or function **knows too much** about another class’s internal details.

---

### Example of tight coupling ❌

`class EmailService {  

sendEmail(msg: string) {}

}  



class NotificationService {   

private emailService = new EmailService();  

notify(msg: string) {     

this.emailService.sendEmail(msg);

}

}`



Problems:

- `NotificationService` depends directly on `EmailService`
    
- If EmailService changes → NotificationService breaks
    
- Hard to test
    
- Hard to extend (SMS, Push)
    

This is **tight coupling**.

---

## Loose Coupling (good design)

### Meaning

> When code depends on **abstractions**, not concrete implementations.

---

### Example of loose coupling ✅



`interface Notification {  

send(msg: string): void;

}



class EmailNotification implements Notification {  

send(msg: string) {}

} 





class NotificationService {   

notify(n: Notification, msg: string) {

n.send(msg);
}

}`


Benefits:

- Easy to extend
    
- No breaking changes
    
- Easy testing
    
- Cleaner code
    

This is **loose coupling**.

---

##  One sentence to remember

> **Tight coupling = change hurts everywhere.  
> Loose coupling = change stays local.**


