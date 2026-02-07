
WHAT IS COMPONENTS IN REACT ? 

In React, a component is a reusable building block used to create user interfaces. A component is usually a JavaScript function that returns JSX, which describes how a part of the UI should appear on the screen. React applications are built by combining multiple components, each responsible for a specific part of the UI, such as a button, form, or header. Components help in reusability, maintainability, and readability of the code because the same UI logic can be reused in multiple places. When the data or state inside a component changes, React automatically re-renders the component to update the UI.



Difference between **Class Components** and **Functional Components** in React

In React, components can be created using **class components** or **functional components**, and both are used to build reusable UI blocks, but they differ in syntax, state handling, and lifecycle management.

**Class components** are ES6 classes that extend `React.Component`. They use a `render()` method to return JSX and manage state using `this.state` and `this.setState()`. Lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` are used to control behavior during different phases of a component’s life. Because of `this` binding and more boilerplate code, class components are harder to read and maintain.

**Functional components**, on the other hand, are simple JavaScript functions that return JSX. Initially, they were stateless, but with the introduction of **Hooks** (like `useState`, `useEffect`, and `useContext`), functional components can now handle state and lifecycle behavior as well. They do not use `this`, have cleaner syntax, are easier to test, and are the **preferred and modern approach** in React today.


### Key differences at a glance

|Feature|Class Component|Functional Component|
|---|---|---|
|Syntax|ES6 class|JavaScript function|
|State|`this.state`|`useState` Hook|
|Lifecycle|Lifecycle methods|`useEffect` Hook|
|`this` keyword|Required|Not used|
|Code size|More boilerplate|Cleaner & shorter|
|Performance|Slightly heavier|Faster & optimized|
|Modern usage|Mostly legacy|Recommended & standard|





### What is JSX in React?

**JSX (JavaScript XML)** is a syntax extension for JavaScript used in React that allows us to write **HTML-like code inside JavaScript**. It makes UI code more readable and expressive by letting developers describe the structure of the user interface in a syntax that looks similar to HTML. Behind the scenes, JSX is **not understood by the browser directly**—it is converted by tools like **Babel** into regular JavaScript function calls (`React.createElement`) before execution.

In JSX, we can embed JavaScript expressions using curly braces `{}`, pass data as props, and dynamically render UI based on logic. JSX also helps React understand the UI structure efficiently so it can update the DOM in an optimized way using the Virtual DOM.


### Key points to remember 

- JSX stands for **JavaScript XML**
    
- It is **not HTML**, but looks like HTML
    
- JSX makes React code **cleaner and more readable**
    
- JavaScript can be written inside JSX using `{ }`
    
- JSX is converted to JavaScript using **Babel**


