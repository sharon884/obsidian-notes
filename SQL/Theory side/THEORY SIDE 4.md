## What are Constraints in SQL? (Simple Explanation)

**Constraints** are **rules applied on table columns** to **restrict the type of data** that can be stored.

They ensure:

- **Data accuracy**
    
- **Data integrity**
    
- **Consistency** in the database
    

👉 In simple words:  
**Constraints stop invalid data from entering the table.**

---

## One-Line Interview Definition (Memorize)

> **“Constraints are rules enforced on database tables to maintain data integrity by restricting invalid data insertion or updates.”**

⏱️ Perfect 15 seconds answer.

---

## Why Constraints Are Important

Without constraints:

- Duplicate data can exist
    
- Invalid values can be inserted
    
- Relationships between tables can break

## Types of Constraints (Very Important for Interview)

### 1️⃣ PRIMARY KEY

- Uniquely identifies each row
    
- Cannot be `NULL`
    
- No duplicates
    

📌 Example:

`id INT PRIMARY KEY`

---

### 2️⃣ FOREIGN KEY

- Creates relationship between tables
    
- Ensures referential integrity
    

📌 Example:

`FOREIGN KEY (dept_id) REFERENCES department(dept_id)`

---

### 3️⃣ UNIQUE

- Prevents duplicate values
    
- Allows `NULL` (usually one)
    

---

### 4️⃣ NOT NULL

- Ensures column cannot be empty
    

---

### 5️⃣ CHECK

- Validates condition before insert/update
    

📌 Example:

`CHECK (age >= 18)`

---

### 6️⃣ DEFAULT

- Assigns default value if none is given
    

📌 Example:

`status VARCHAR(10) DEFAULT 'active'`