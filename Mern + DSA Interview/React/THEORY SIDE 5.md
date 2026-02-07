
 How JSX converts to JS (Babel → React.createElement → Virtual DOM)


**JSX is not understood by the browser, so at build time Babel converts JSX into normal JavaScript using `React.createElement`. This JavaScript does not create HTML directly; instead, when the application runs in the browser, React executes this code and creates Virtual DOM objects, which are lightweight JavaScript objects stored in memory. These objects are combined to form a Virtual DOM tree. Whenever state or props change, React creates a new Virtual DOM tree and compares it with the previous one using a process called diffing. After identifying what exactly has changed, React updates only those specific parts in the Real DOM, and this efficient update process is called reconciliation.**

---


## Transpiler (Babel)

A **transpiler** is a tool that converts **modern JavaScript code into older, browser-compatible JavaScript**. **Babel** is a JavaScript transpiler commonly used in React applications to convert **JSX and modern JavaScript (ES6+)** into plain JavaScript that browsers can understand. Babel runs at **build time**, not in the browser, and ensures that React code works consistently across different browsers.


A transpiler is a tool that converts code written in one language or syntax into another language or syntax at the same level. Babel is an example of a JavaScript transpiler. In React, Babel converts JSX and modern JavaScript syntax into normal JavaScript that browsers can understand. This conversion happens at build time, and after that, the browser directly executes the compiled JavaScript at runtime without needing Babel.

### Ultra-short interview version 

> _A transpiler converts one language to another, and Babel is a JavaScript transpiler that converts JSX into browser-compatible JavaScript in React._