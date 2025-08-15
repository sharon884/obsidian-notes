
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



## [Constants](https://javascript.info/variables#constants)

To declare a constant (unchanging) variable, use `const` instead of `let`:

```javascript
const myBirthday = '18.04.1982';
```

Variables declared using `const` are called “constants”. They cannot be reassigned. An attempt to do so would cause an error:

[](https://javascript.info/variables# "run")

[](https://javascript.info/variables# "open in sandbox")

```javascript
const myBirthday = '18.04.1982';

myBirthday = '01.01.2001'; // error, can't reassign the constant!
```

When a programmer is sure that a variable will never change, they can declare it with `const` to guarantee and communicate that fact to everyone.


## [Summary](https://javascript.info/variables#summary)

We can declare variables to store data by using the `var`, `let`, or `const` keywords.

- `let` – is a modern variable declaration.
- `var` – is an old-school variable declaration. Normally we don’t use it at all, but we’ll cover subtle differences from `let` in the chapter [The old "var"](https://javascript.info/var), just in case you need them.
- `const` – is like `let`, but the value of the variable can’t be changed.

Variables should be named in a way that allows us to easily understand what’s inside them.