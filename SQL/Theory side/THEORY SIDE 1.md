
## What is a **Database**?
A **database** is an **organized collection of data** stored so that it can be:

- easily **stored**
    
- easily **retrieved**
    
- easily **updated**
    
- easily **deleted**


### Technical definition

> A database is a structured collection of related data stored electronically in a computer system.



## What is **DBMS** (Database Management System)?

### Simple definition

A **DBMS** is **software** that helps you:

- create databases
    
- store data
    
- retrieve data
    
- manage data safely
    

👉 If **Database = data**,  
then **DBMS = manager of that data**

### Examples of DBMS

- MySQL
    
- PostgreSQL
    
- Oracle
    
- MongoDB
    
- SQLite

### What DBMS does for you

Without DBMS ❌:

- You manually store files
    
- No security
    
- No backup
    
- Data corruption possible
    

With DBMS ✅:

- Security (users, passwords)
    
- Backup & recovery
    
- Data consistency
    
- Query language (SQL)
    

💡 **Key idea**:  
DBMS is the **bridge** between **you** and the **database**.


## What is **RDBMS** (Relational DBMS)?

### Simple definition

An **RDBMS** is a **type of DBMS** that stores data in the form of:

- **tables**
    
- with **relations** between them
    

👉 RDBMS = DBMS + **relationships**

### Examples of RDBMS

- MySQL
    
- PostgreSQL
    
- Oracle
    
- SQL Server
    

### Why “Relational”?

Because:

- Data is stored in **tables**
    
- Tables are connected using **keys**
    

Example:

- `users` table
    
- `orders` table  
    Connected using `user_id`
    

💡 **Key idea**:  
RDBMS follows **rules** (relational model) → more powerful & reliable.



## Difference: **DBMS vs RDBMS**

|Feature|DBMS|RDBMS|
|---|---|---|
|Data storage|Files / tables|Tables only|
|Relationships|❌ Not supported|✅ Supported|
|Normalization|❌ No|✅ Yes|
|Primary Key|❌ Not required|✅ Mandatory|
|Data integrity|Weak|Strong|
|Example|File system DB|MySQL, PostgreSQL|

### One-line interview answer 

> DBMS manages data, whereas RDBMS manages **related data using tables with constraints**.

