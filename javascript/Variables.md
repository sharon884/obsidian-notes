
Variables are used to store this information.

## [A variable](https://javascript.info/variables#a-variable)

A [variable](https://en.wikipedia.org/wiki/Variable_\(computer_science\)) is a “named storage” for data. We can use variables to store goodies, visitors, and other data.


- In JavaScript, **`var`, `let`, and `const` are keywords**.
    
- Their purpose: **to declare variables**.

```javascript
let message;

message = 'Hello'; // store the string 'Hello' in the variable named message
```

The string is now saved into the memory area associated with the variable. We can access it using the variable name:

```javascript
let message;

message = 'Hello!';

message = 'World!'; // value changed

alert(message);
```

When the value is changed, the old data is removed from the variable:



Declaring twice triggers an error

A variable should be declared only once.

A repeated declaration of the same variable is an error:

[](https://javascript.info/variables# "run")

[](https://javascript.info/variables# "open in sandbox")

```javascript
let message = "This";

// repeated 'let' leads to an error
let message = "That"; // SyntaxError: 'message' has already been declared
```

So, we should declare a variable once and then refer to it without `let`.