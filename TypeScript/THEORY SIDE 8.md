
<h1>void and never </h1>
## `void`

### What it means

> **`void` means a function does not return any value.**

`function logMessage(msg: string): void {  

console.log(msg); 

}`

- Function runs
    
- Side effects happen
    
- **Nothing meaningful is returned**
    

 Technically it returns `undefined`, but we **don’t care about the value**.

---

### When to use `void`

- Logging
    
- Event handlers
    
- Functions that only perform actions
    

`button.addEventListener("click", (): void => {  

console.log("clicked"); 

});`

---

## `never`

### What it means

> **`never` means the function never finishes normally.**

It **never returns** — not even `undefined`.

`function throwError(msg: string): never {

throw new Error(msg); 

}`

---

### Common cases for `never`

#### 1️⃣ Function that always throws

`function fail(): never {  

throw new Error("Crash"); 

}`

#### 2️⃣ Infinite loop

`function infinite(): never {  

while (true) {}

}`

---

## `void` vs `never` (Core Difference)

|Feature|`void`|`never`|
|---|---|---|
|Returns normally|✅ Yes|❌ No|
|Returns `undefined`|✅|❌|
|Function completes|✅|❌|
|Common use|Side effects|Errors / infinite loops|

---

## Important Interview Trap ⚠️void
What it means

void means a function does not return any value.

function logMessage(msg: string): void {
  console.log(msg);
}


Function runs

Side effects happen

Nothing meaningful is returned

⚠️ Technically it returns undefined, but we don’t care about the value.

When to use void

Logging

Event handlers

Functions that only perform actions

button.addEventListener("click", (): void => {
  console.log("clicked");
});

never
What it means

never means the function never finishes normally.

It never returns — not even undefined.

function throwError(msg: string): never {
  throw new Error(msg);
}

Common cases for never
1️⃣ Function that always throws
function fail(): never {
  throw new Error("Crash");
}

2️⃣ Infinite loop
function infinite(): never {
  while (true) {}
}

void vs never (Core Difference)
Feature	void	never
Returns normally	✅ Yes	❌ No
Returns undefined	✅	❌
Function completes	✅	❌
Common use	Side effects	Errors / infinite loops
Important Interview Trap ⚠️

❌ Wrong:

function test(): never {
  console.log("hi");
}


Because it finishes execution.

never in Type Narrowing (Advanced 💡)
function handle(value: string | number) {
  if (typeof value === "string") {
    return;
  }
  if (typeof value === "number") {
    return;
  }

  // value is never here
}


If a new type is added later, TypeScript will warn you — very useful!

One-Line Interview Answers 🎯

void:

Used when a function does not return a value.

never:

Used when a function never completes or never returns.

Ultra-Short Version

void → returns nothing
never → never returns

❌ Wrong:

`function test(): never { 

console.log("hi");

}`

Because it **finishes execution**.

---

## `never` in Type Narrowing 

`function handle(value: string | number) {

if (typeof value === "string") { 

return; 

} 


if (typeof value === "number") {    

return; 

}    // value is never here 

}`

If a new type is added later, TypeScript will warn you — very useful!

---

## One-Line Interview Answers 

**`void`:**

> Used when a function does not return a value.

**`never`:**

> Used when a function never completes or never returns.

---

## Ultra-Short Version

> **`void` → returns nothing  
> `never` → never returns**

---