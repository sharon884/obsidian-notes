

ACID = Atomicity, Consistency, Isolation, Durability

“ACID properties in SQL are a set of guarantees that ensure database transactions are reliable and maintain data integrity.  
Atomicity means a transaction is treated as a single unit—either all operations succeed or all are rolled back.  
Consistency ensures the database moves from one valid state to another while following all constraints and rules.  
Isolation ensures that multiple transactions running concurrently do not interfere with each other.  
Durability guarantees that once a transaction is committed, the data is permanently saved, even in case of system failure.”


## What is Normalization? (Simple Explanation)

**Normalization** is the process of **organizing data in a database** to:

- Reduce **data redundancy** (duplicate data)
    
- Avoid **data inconsistency**
    
- Improve **data integrity**
    

In simple words 👉  
👉 **store data in the right place, in the right way**

---

## Why Do We Need Normalization?

Without normalization:

- Same data is stored multiple times
    
- Updating data becomes risky
    
- Deleting data may cause data loss
    
- Inserting data becomes difficult
    

These are called:

- **Insertion anomaly**
    
- **Update anomaly**
    
- **Deletion anomaly**
    

---

## One-Line Definition (Interview-Safe)

> **“Normalization is the process of organizing database tables to reduce redundancy and avoid data anomalies by dividing data into multiple related tables.”**



## First Normal Form (1NF)

---

## What is 1NF? (Simple Explanation)

A table is in **First Normal Form (1NF)** if:

1. Each column contains **atomic (indivisible) values**
    
2. No **repeating groups** or **multi-valued attributes**
    
3. Each row can be uniquely identified (primary key)

**One cell = one value**

---

## Why 1NF is Needed

Without 1NF:

- Data becomes hard to query
    
- Searching and updating becomes complex
    
- Violates basic relational rules

## nterview One-Liner (Very Important)

> **“A table is in First Normal Form if each column contains atomic values and there are no repeating groups or multi-valued attributes.”**



## econd Normal Form (2NF)

---

## What is 2NF? (Simple Explanation)

A table is in **Second Normal Form (2NF)** if:

1. It is already in **1NF**
    
2. It has **no partial dependency**
    

👉 **Partial dependency** =  
A non-key column depends on **part of a composite primary key**, not the full key.


## Third Normal Form (3NF)

---

## What is 3NF? (Simple Explanation)

A table is in **Third Normal Form (3NF)** if:

1. It is already in **2NF**
    
2. It has **no transitive dependency**
    

👉 **Transitive dependency** =  
A non-key column depends on **another non-key column**, instead of directly on the primary key.


## What is BCNF? (Simple Explanation)

**BCNF** is a **stronger version of 3NF**.

A table is in **BCNF** if:

👉 **For every functional dependency, the left side must be a super key.**

In simple words:

- Every determinant must be a **candidate key**
    

---

## Why Do We Need BCNF?

Even after **3NF**, some **anomalies can still exist** when:

- A table has **multiple candidate keys**
    
- Dependencies overlap
    

BCNF fixes these edge cases.