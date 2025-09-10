
Event propagation in JavaScript is the way events move through the DOM tree when an event is triggered. It has two main phases:

### 🔄 The Three Phases of Event Propagation

1. **Capturing Phase (a.k.a. “trickle down” phase)**
    
    - Event starts at the top: `window → document → <html> → <body> → <div> → <button>`
        
    - At this stage, the event is just “passing through” each ancestor on its way down to the target.
        
    - If you attach a listener with:
        
        `element.addEventListener("click", handler, true); // true = capture`
        
        it will fire **during capturing**.
        

---

2. **Target Phase**
    
    - The event reaches the target element itself (in this case, the `<button>`).
        
    - Event listeners on the button are triggered (first capturing listeners on the button, then bubbling listeners on the button).
        

---

3. **Bubbling Phase (a.k.a. “bubble up” phase)**
    
    - After the target, the event **travels upward**: `button → div → body → html → document → window`.
        
    - By default (`addEventListener("click", handler)` with no third argument), handlers are executed during this phase.
        
    - This is why bubbling is used in techniques like **event delegation**.

### 🛑 Stopping Propagation

- `event.stopPropagation()` → stops the event from going further (either down or up depending on the phase).
    
- `event.stopImmediatePropagation()` → stops it completely, even other listeners on the same element.



Capturing: Window → Document → HTML → Body → Div → Button
Target:    Button
Bubbling:  Button → Div → Body → HTML → Document → Window

**Simple way to remember**:

- Capturing = _top → down_
    
- Bubbling = _down → top_
    
- Target = _middle point_

