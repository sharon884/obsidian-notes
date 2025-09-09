

### 1. **Rounding & Numbers**

`Math.floor(4.9);  // 4   → always down

Math.ceil(4.1);   // 5   → always up 

Math.round(4.5);  // 5   → nearest integer 

Math.trunc(4.9);  // 4   → just remove decimals`

👉 Used for **prices, pagination, indexes, percentages, etc.**

---

### 2. **Absolute Value & Sign**

`Math.abs(-10);   // 10 

Math.sign(-10);  // -1`

👉 Used when working with **distances, balances, coordinates.**

---

### 3. **Random**

`Math.random();               // 0 ≤ num < 1

Math.floor(Math.random()*10) // 0–9

Math.floor(Math.random()*100)+1 // 1–100`

👉 Used for **games, OTPs, random IDs, shuffling.**

---

### 4. **Min & Max**

`Math.min(5, 2, 9);  // 2

Math.max(5, 2, 9);  // 9`

👉 Used for **finding highest/lowest scores, prices, etc.**

---

### 5. **Powers & Roots**

`Math.pow(2, 3);  // 8 

Math.sqrt(16);   // 4`

👉 Used in **geometry, physics, scaling values.**

---

### 6. **Constants**

`Math.PI  // 3.14159 (circle, angles)

Math.E   // 2.718   (growth, logs sometimes)`

👉 Used in **circle area, trigonometry, formulas.**

---

### 7. **Trigonometry (basic)**

`Math.sin(Math.PI/2); // 1

Math.cos(0);         // 1

Math.tan(Math.PI/4); // 1`

👉 Mostly used in **animations, graphics, physics engines.**

---

✅ So, in day-to-day development, you’ll mostly use:

- `Math.floor`
    
- `Math.ceil`
    
- `Math.round`
    
- `Math.random`
    
- `Math.min` / `Math.max`
    
- `Math.abs`
    
- `Math.sqrt` / `Math.pow`
    
- `Math.PI`
    

The rest are **specialized** and not needed often.