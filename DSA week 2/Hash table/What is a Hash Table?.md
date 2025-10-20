## 🧠 1. What is a Hash Table?

A **Hash Table** is a data structure that **stores data in key-value pairs** for **very fast access** — usually in **O(1)** time.  
Think of it as a “super-fast dictionary” where each key directly points to where its value is stored in memory.

---

## ⚙️ 2. Internal Working (Step-by-Step)

Let’s understand what happens **inside** when you store or get a value.

### ➤ Step 1: You give a key

Example:

`key = "name" value = "Champ"`

### ➤ Step 2: Hash Function

A **hash function** takes the key (`"name"`) and **converts it into a numeric index** (like `3`) based on the table’s size.

👉 Example:  
Let’s say our hash table array has size `10`.  
Then:

`hash("name") → 3`

### ➤ Step 3: Store value at that index

`index 3 → "Champ"`

So internally it looks like:

`[ , , , "Champ", , , , , , ]`

---

## 🔍 3. Lookup Operation (you asked what it means)

Yes, Champ, you’re correct — **lookup means searching**.

- When you do something like `hashTable.get("name")`
    
- The hash function again computes the **same index (3)** for `"name"`
    
- Then directly goes to that index in **O(1)** time to retrieve the value.
    

So:  
📦 `hashTable["name"] → "Champ"`

That’s why lookup (searching by key) in hash tables is **super fast** — because there’s no need to traverse an array or linked list.

---

## ⚔️ 4. Collision — When Two Keys Hash to Same Index

Example:

`hash("name") → 3 hash("game") → 3`

Now both want to store values in index 3. That’s called a **collision**.

---

## 🪄 5. Collision Handling Methods

There are two main ways:

### (A) **Chaining** (most common)

- Each index of the array stores a **linked list** (or array) of key-value pairs.
    
- If two keys hash to the same index, they’re stored in the same linked list.
    

Example:

`index 3 → [ ("name", "Champ"), ("game", "Cricket") ]`

When searching, it just checks the small list inside that bucket.

---

### (B) **Open Addressing**

- Instead of making a linked list, it **finds another empty slot** in the array to store the new value.
    
- Methods: Linear probing, Quadratic probing, Double hashing.
    

---

## ⏱️ 6. Time Complexity Summary

|Operation|Average Case|Worst Case|
|---|---|---|
|Insertion|O(1)|O(n) (if many collisions)|
|Lookup|O(1)|O(n)|
|Deletion|O(1)|O(n)|

---

## 🧩 7. Why Hash Table is Fast?

Because:

1. **Keys are not searched one by one.**
    
2. **Hash function** calculates a **direct index** to jump to.
    

That’s why it’s used in:

- Caching
    
- Databases
    
- Symbol tables in compilers
    
- Maps / Objects in JavaScript
    

---

## 🔁 8. Real-world Analogy

Imagine you have 100 lockers (array size 100).  
You don’t search each locker — you calculate locker number by your name (hash).  
If two people get the same locker number → collision → share a sub-locker (linked list).