

“In JavaScript, methods like `getElementById`, `getElementsByClassName`, `getElementsByTagName`, `querySelector`, and `querySelectorAll` are used to **select HTML elements from the DOM**.

These methods act as a bridge between JavaScript and the DOM, allowing us to **interact with and manipulate HTML elements** — for example, changing their content, applying styles, updating attributes, or adding event listeners.”

### 🔹 1. Element Selection

- `document.getElementById("id")` → Select by id.
    
- `document.getElementsByClassName("class")` → Select by class (HTMLCollection).
    
- `document.getElementsByTagName("tag")` → Select by tag name.
    
- `document.querySelector("cssSelector")` → First match of a CSS selector.
    
- `document.querySelectorAll("cssSelector")` → All matches (NodeList).
    

---

### 🔹 2. Creating and Inserting Elements

- `document.createElement("tag")` → Create a new element.
    
- `element.appendChild(child)` → Add a child inside an element.
    
- `element.append(node1, node2)` → Add multiple nodes or text.
    
- `element.prepend(node)` → Insert at the beginning.
    
- `element.insertBefore(newNode, referenceNode)` → Insert before a specific node.
    

---

### 🔹 3. Removing or Replacing Elements

- `element.remove()` → Remove an element.
    
- `parent.removeChild(child)` → Remove a child element.
    
- `parent.replaceChild(newChild, oldChild)` → Replace an element.
    

---

### 🔹 4. Modifying Content & Attributes

- `element.textContent` → Get or set text.
    
- `element.innerHTML` → Get or set HTML.
    
- `element.setAttribute("attr", "value")` → Set an attribute.
    
- `element.getAttribute("attr")` → Get an attribute.
    
- `element.removeAttribute("attr")` → Remove an attribute.
    

---

### 🔹 5. Styling & Classes

- `element.style.color = "red"` → Change style inline.
    
- `element.classList.add("className")` → Add a class.
    
- `element.classList.remove("className")` → Remove a class.
    
- `element.classList.toggle("className")` → Add/remove class dynamically.
    
- `element.classList.contains("className")` → Check if class exists.
    

---

### 🔹 6. Events (Very Important)

- `element.addEventListener("click", function)` → Attach event handler.
    
- `element.removeEventListener("click", function)` → Remove event handler.
    

---

## 🎯 Interview One-Liner

“JavaScript provides multiple DOM methods for interacting with elements — selection methods (`getElementById`, `querySelector`), creation methods (`createElement`, `appendChild`), modification methods (`innerHTML`, `setAttribute`), and event handling methods (`addEventListener`). Together, these allow us to fully manipulate the DOM.”


