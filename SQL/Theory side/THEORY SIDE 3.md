

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

