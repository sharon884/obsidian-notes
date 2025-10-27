
## 🔎 What is Event Delegation?

Event delegation is a **technique** in JavaScript where instead of attaching event listeners to many child elements, you attach **one listener to a parent element** and let **event bubbling** handle the rest.

- Events bubble up from the child to the parent.
    
- The parent’s listener can detect which child triggered the event using `event.target`.



Without delegation, you’d need to attach an event to **each button**:
❌ Problem: Inefficient, more memory usage, hard to manage.

## ✅ Benefits of Event Delegation

1. **Performance**: Fewer event listeners → less memory usage.
    
2. **Dynamic Elements**: Works for elements added later without re-attaching listeners.
    
3. **Cleaner Code**: One listener instead of many.
    

---

## ⚡ Interview-Ready One-Liner

“Event delegation is a technique where we attach a single event listener to a parent element and handle events on child elements through event bubbling, instead of adding listeners to each child individually.”


