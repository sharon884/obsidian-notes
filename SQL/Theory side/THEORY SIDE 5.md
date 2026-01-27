## What are Relationships in SQL? (Simple Explanation)

**Relationships** define **how tables are connected to each other** in a database.

They are created using **primary keys and foreign keys** to maintain **data consistency and integrity**.

## One-Line Interview Definition (Must Memorize)

> **“A relationship in SQL defines how tables are connected using primary and foreign keys to maintain referential integrity.”**

⏱️ 15 seconds. Perfect.

---

## Types of Relationships (Very Important)

### 1️⃣ One-to-One (1:1)

**Meaning:**

- One row in table A → one row in table B
    

**Example:**

- User → UserProfile
    

📌 Implementation:

- Foreign key with UNIQUE constraint
    

---

### 2️⃣ One-to-Many (1:N) ✅ (Most Common)

**Meaning:**

- One row in table A → many rows in table B
    

**Example:**

- One Department → many Employees
    

📌 Implementation:

- Foreign key in the “many” table
    

`employee.dept_id → department.dept_id`

---

### 3️⃣ Many-to-Many (M:N)

**Meaning:**

- Many rows in table A → many rows in table B
    

**Example:**

- Students ↔ Courses
    

📌 Implementation:

- **Junction (bridge) table**
    

`student_course (student_id, course_id)`

---

## How YOU Should Say This in Interview (Clean Flow)

> “Relationships in SQL describe how tables are connected. The common types are one-to-one, one-to-many, and many-to-many. These relationships are implemented using primary keys and foreign keys to maintain referential integrity.”

---