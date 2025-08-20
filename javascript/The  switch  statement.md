
# The "switch" statement

A `switch` statement can replace multiple `if` checks.

It gives a more descriptive way to compare a value with multiple variants.



### 📌 Basic Syntax

`switch (expression) 
{   case value1:     // Code runs if expression === value1     break;
case value2:     // Code runs if expression === value2     break;
default:     // Runs if no case matches }`

---

### ✅ Rules

- `switch` evaluates an **expression**.
    
- `case` checks for **strict equality (===)**.
    
- If a case matches, code executes **until a break** is found.
    
- If no `break`, execution **falls through** to the next case.
    
- `default` is optional, runs when no case matches.
    

---

### ⚡ Example

`let fruit = "apple"; 
switch (fruit) {  
case "banana": 
console.log("Yellow fruit");  
break; 
case "apple":
console.log("Red fruit");
break; 
default:   
console.log("Unknown fruit"); } 
// Output: Red fruit`

---

### 🎯 Fall-through Example (no break)

`let grade = "B";
switch (grade) {
case "A":
case "B":  
console.log("Good job!");
break;   
case "C": 
console.log("Passed");
break; 
default:   
console.log("Try again"); }
// Output: Good job!`

---

### 📌 When to Use Switch

- When you have **multiple conditions** on a **single variable**.
    
- Makes code more **readable** than multiple `if...else if`.
    

---

📋 **Quick Reference**

|Keyword|Meaning|
|---|---|
|`switch`|Starts the block with an expression to test|
|`case`|Checks if expression matches the case value|
|`break`|Exits the switch after a match|
|`default`|Executes if no case matches|
|Fall-through|If `break` is missing, execution continues to next case|


