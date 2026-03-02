
# What Actually Happens If a Class Has 5 Responsibilities?

If a class has multiple responsibilities:

### 1️⃣ Multiple Reasons to Change

If:

- Database logic changes
    
- Business logic changes
    
- Validation changes
    
- Logging changes
    

You must modify the same class again and again.

That violates SRP.

---

### 2️⃣ High Risk of Breaking Code

When you change one functionality,  
you might accidentally break another.

Because everything is tightly packed together.

---

### 3️⃣ Hard to Test

If one class does too much:

- You cannot unit test parts independently.
    
- You must mock too many dependencies.
    

---

### 4️⃣ Low Reusability

You cannot reuse just one behavior.  
You are forced to take the entire class.

---

### 5️⃣ Poor Readability

The class becomes:

- Long
    
- Confusing
    
- Hard to understand
    

---

#  The Real Definition of SRP

> A class should have only one reason to change.

Not “one function”.  
Not “one method”.

One **responsibility**.

Responsibility = one job.