

## **1️⃣ Bubble Sort**

- **Key Idea:** Compare **adjacent elements** and swap if out of order.
    
- **Sorted / Unsorted:** No explicit sorted subarray at start — array gradually becomes sorted from **end to start**.
    
- **Operation:** **Swapping** happens repeatedly for each pair.
    
- **Optimization:** Use a **swapped flag** to stop early if no swaps occur.
    

**Flow Example:**

`Array: [5, 2, 4, 6, 1]  Pass 1: Compare 5-2 → swap → [2,5,4,6,1]         Compare 5-4 → swap → [2,4,5,6,1]         Compare 5-6 → no swap → [2,4,5,6,1]         Compare 6-1 → swap → [2,4,5,1,6]  Next pass continues until no swaps occur`

**Complexity:**

- Best: O(n) (optimized)
    
- Average/Worst: O(n²)
    
- Space: O(1)
    

---

## **2️⃣ Selection Sort**

- **Key Idea:** Find the **smallest (or largest)** element from **unsorted array** and place it at the end of **sorted subarray**.
    
- **Sorted / Unsorted:** Left part grows as sorted, right part is unsorted.
    
- **Operation:** **One swap per outer loop** (after finding min element).
    

**Flow Example:**

`Array: [5, 2, 4, 6, 1]  Pass 1: Find min=1 → swap with first → [1,2,4,6,5] Pass 2: Find min=2 → already in place → [1,2,4,6,5] Pass 3: Find min=4 → already in place → [1,2,4,6,5] Pass 4: Find min=5 → swap with 6 → [1,2,4,5,6]`

**Complexity:**

- Best/Average/Worst: O(n²)
    
- Space: O(1)
    
- Notes: Fewer swaps than Bubble Sort, but not adaptive.
    

---

## **3️⃣ Insertion Sort**

- **Key Idea:** Take each element from **unsorted subarray** and insert it into the correct position in the **sorted subarray**.
    
- **Sorted / Unsorted:** Left part = sorted, right part = unsorted.
    
- **Operation:** **Shifting elements** (not swapping) to make space for insertion.
    

**Flow Example:**

`Array: [5, 2, 4, 6, 1]  Step 1: key=2 → shift 5 → insert 2 → [2,5,4,6,1] Step 2: key=4 → shift 5 → insert 4 → [2,4,5,6,1] Step 3: key=6 → no shift → insert 6 → [2,4,5,6,1] Step 4: key=1 → shift 2,4,5,6 → insert 1 → [1,2,4,5,6]`

**Complexity:**

- Best: O(n) (already sorted)
    
- Average/Worst: O(n²)
    
- Space: O(1)
    
- Notes: Very efficient for **nearly sorted arrays**.
    

---

### 🔹 **Quick Comparison**

|Algorithm|Key Operation|Sorted/Unsorted|Adaptive?|Swaps/Shifts|
|---|---|---|---|---|
|Bubble Sort|Swap adjacent|No explicit sorted at start|✅ (optimized)|Many swaps|
|Selection Sort|Pick min & swap|Left grows as sorted|❌|One swap per pass|
|Insertion Sort|Shift & insert|Left = sorted, right = unsorted|✅|Shifts elements instead of swapping|

---

💡 **Memory Tip:**

- **Bubble:** “Bubble up → swap adjacent repeatedly.”
    
- **Selection:** “Pick min → put in sorted left.”
    
- **Insertion:** “Pick key → shift → insert into sorted left.”