

### **1. While Loop**

- Runs **as long as condition is true**.
    
- Condition is checked **before** each iteration.
    

`let i = 0; while (i < 3) {   console.log(i); // 0, 1, 2   i++; }`

---

### **2. Do...While Loop**

- Runs **at least once** (because body executes before checking).
    
- Then continues while condition is true.
    

`let i = 0; do {   console.log(i); // 0, 1, 2   i++; } while (i < 3);`

---

### **3. For Loop**

- Best for **counting / fixed number of iterations**.
    
- Has 3 parts: _init_; _condition_; _increment/decrement_.
    

`for (let i = 0; i < 3; i++) {   console.log(i); // 0, 1, 2 }`



📌 **Quick Table for Loops**

| Loop         | Condition check | Runs at least once? | Usage              |
| ------------ | --------------- | ------------------- | ------------------ |
| `while`      | Before body     | ❌ (No)              | Unknown iterations |
| `do...while` | After body      | ✅ (Yes)             | Must run once      |
| `for`        | Before body     | ❌ (No)              | Known iterations   |


# 🚦 Break & Continue


### **Break**

- Immediately **stops the loop**.
    
- Exits out completely.
    

`for (let i = 0; i < 5; i++) {   if (i === 3) break;   console.log(i); // 0, 1, 2 }`

---

### **Continue**

- **Skips current iteration**, goes to next loop cycle.
    

`for (let i = 0; i < 5; i++) {   if (i === 2) continue;   console.log(i); // 0, 1, 3, 4 }`


