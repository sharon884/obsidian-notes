

## 🧠 What does a Hash Function do?

A **hash function** takes your **key (string, number, etc.)** and converts it into a **numeric index** that fits inside the array used by the hash table.

So basically:

`key → hash function → index`

For example:

`"name" → 3 "age" → 7 "country" → 1`

---

## ⚙️ How does it do that?

Let's assume we have an array of fixed size, say `10`.

Now, we need a function that can:

1. Take the key (like `"name"`)
    
2. Convert it into a number
    
3. Make sure that number is **within 0–9**
    

---

### ✅ Step 1: Convert key to numeric value

Since keys like `"name"` are strings, the hash function will usually:

- Take each **character** of the string
    
- Convert it into its **ASCII (Unicode) code**
    
- Add them together (or mix them mathematically)
    

Example:

`"name" n → 110 a → 97 m → 109 e → 101 Total = 110 + 97 + 109 + 101 = 417`

So, we got **417** from the string `"name"`.

---

### ✅ Step 2: Fit the number inside the array size

Now we need an index between **0 and 9** (because array size = 10).

We can use the **modulus operator (%)**:

`417 % 10 = 7`

So, `"name"` will be stored at index **7**.

---

### ✅ Step 3: That’s your hash function!

So internally, it’s like:

`function hash(key) {   let hashValue = 0;   for (let i = 0; i < key.length; i++) {     hashValue += key.charCodeAt(i);   }   return hashValue % 10;  // fit within array size }  console.log(hash("name")); // e.g., 7 console.log(hash("age"));  // maybe 2`

---

## 🧩 So how does it connect with storing data?

When we insert into a hash table:

`insert("name", "Champ")`

1. Hash function computes → index `7`
    
2. The value `"Champ"` is stored at `table[7]`
    

When we do:

`get("name")`

1. Hash function again computes index `7`
    
2. Hash table goes directly to `table[7]` and returns `"Champ"`
    

That’s why **lookup is O(1)** → because it jumps straight to the right index instead of searching through all keys.

---

## ⚠️ Important: Why can collisions still happen?

Because two different keys can sometimes produce the **same hash value**.

Example:

`hash("name") → 7 hash("mane") → 7`

Different keys, same index → **collision**  
That’s where **chaining or open addressing** come into play to handle that.