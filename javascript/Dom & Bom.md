
# 🔹 DOM (Document Object Model)

- The **DOM** is an **object representation of the HTML document**.
    
- When the browser loads a web page, it converts HTML into a **tree structure (nodes)** called the DOM.
    
- JavaScript can then **read, modify, create, or delete** elements via the DOM.
    

👉 Example:

`<html>   <body>     <h1>Hello</h1>   </body> </html>`

The browser creates a DOM tree:

`Document  └── html       └── body            └── h1 ("Hello")`

So when you write:

`document.querySelector("h1").textContent = "Hi DOM!";`

➡️ It changes the actual web page dynamically.

✔️ **Key point**: DOM = API that allows JavaScript to interact with HTML elements.

---

# 🔹 BOM (Browser Object Model)

- The **BOM** is everything the browser provides **outside of the DOM**.
    
- It gives JavaScript access to the **browser features** (not the page itself).
    
- Examples: `window`, `navigator`, `screen`, `location`, `history`.
    

👉 Example:

`console.log(window.innerWidth);  // Browser window width console.log(location.href);      // Current page URL console.log(navigator.userAgent); // Browser details history.back();                  // Go to previous page`

✔️ **Key point**: BOM = API to interact with the **browser environment**, not the page.

---

# 🔹 DOM vs BOM (Interview Ready)

| Feature    | DOM                                              | BOM                                          |
| ---------- | ------------------------------------------------ | -------------------------------------------- |
| Definition | Object model of the HTML document                | Object model of the browser                  |
| Purpose    | Work with **page content** (HTML, CSS)           | Work with **browser features**               |
| Examples   | `document`, `element.innerHTML`, `querySelector` | `window`, `navigator`, `location`, `history` |
| Usage      | Change text, styles, structure of page           | Get browser info, redirect, resize window    |


# 🔹 JSinfo style summary

- **DOM** = document as an object → edit content & structure.
    
- **BOM** = browser as an object → work with browser itself.
    
- Both are accessible via the **global object `window`**.



### 🔹 How the DOM Tree is Created

When the browser loads an HTML file, it **parses the HTML code line by line**.

- Every **HTML tag** becomes a **node**.
    
- Nested tags become **child nodes**.
    
- Text inside tags becomes a **text node**.
    

This creates a **tree-like structure** called the **DOM Tree**.


### Why a “Tree”?

- Each node can have **children** (like `<body>` has `<h1>` and `<p>`).
    
- The structure starts with one **root (`document`)** → like a tree trunk.
    
- Branches (child nodes) grow from it → like a real tree.


## 🔹 Who converts HTML → DOM?

The **browser’s rendering engine** does the conversion.

- Every browser (Chrome, Firefox, Safari, Edge) has a **rendering engine**.
    
- Examples:
    
    - Chrome/Edge → **Blink**
        
    - Firefox → **Gecko**
        
    - Safari → **WebKit**
        

---

### 🔹 Process (simplified)

1. **Browser receives HTML (text)** from server.
    
2. The **HTML parser** (part of the rendering engine) reads it line by line.
    
3. It creates **tokens** for tags (`<html>`, `<body>`, etc.).
    
4. Tokens are converted into **nodes**.
    
5. Nodes are linked together into the **DOM tree**.
    

So basically:

**HTML text → (parsed by rendering engine) → DOM tree in memory**


### 🔹 Key Interview Point

- **Developer writes HTML (text)**.
    
- **Browser parses it** using the rendering engine.
    
- **Browser creates the DOM tree in memory**.
    
- **JavaScript interacts with the DOM tree**, not raw HTML.

