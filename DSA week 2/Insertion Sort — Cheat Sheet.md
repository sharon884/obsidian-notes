### 🔹 Concept

Insertion Sort builds a **sorted subarray** step by step.  
At each iteration, it **picks one element** from the unsorted part and **inserts** it into the correct position inside the sorted subarray.

---

### 🔹 Core Idea

- Split array into **two parts**:
    
    - ✅ **Sorted subarray** (left side)
        
    - ❌ **Unsorted subarray** (right side)
        
- Take the **first element** of the unsorted part (`current`),  
    and **shift** all elements in the sorted part **that are greater than it** to the right.
    
- Then **insert** `current` in the right place.
    

---

### 🔹 Algorithm Steps

`function insertionSort(arr) {   for (let i = 1; i < arr.length; i++) {     let current = arr[i];     let j = i - 1;      while (j >= 0 && arr[j] > current) {       arr[j + 1] = arr[j]; // shift element right       j--;     }      arr[j + 1] = current; // insert current element   }    return arr; }`

---

### 🔹 Example Walkthrough

Array: `[2, 1, 3, 6, 5]`

|Step|i|current|Action|Result|
|---|---|---|---|---|
|1|1|1|2 > 1 → shift 2 → insert 1|[1, 2, 3, 6, 5]|
|2|2|3|already in correct place|[1, 2, 3, 6, 5]|
|3|3|6|already in correct place|[1, 2, 3, 6, 5]|
|4|4|5|6 > 5 → shift → insert 5|[1, 2, 3, 5, 6]|

✅ Final Sorted Array → `[1, 2, 3, 5, 6]`

---

### 🔹 Characteristics

|Property|Description|
|---|---|
|**Time Complexity (Worst)**|O(n²) — nested loops (e.g., reverse sorted array)|
|**Time Complexity (Best)**|O(n) — already sorted array|
|**Space Complexity**|O(1) — in-place sort|
|**Stable**|✅ Yes (preserves order of equal elements)|
|**In-place**|✅ Yes (no extra array used)|
|**Adaptive**|✅ Yes (stops early if array nearly sorted)|

---

### 🔹 Key Difference from Others

|Algorithm|How it Works|Core Action|
|---|---|---|
|**Bubble Sort**|Repeatedly swaps adjacent elements|Swap|
|**Selection Sort**|Finds min element and swaps once per pass|Find minimum|
|**Insertion Sort**|Inserts each element into correct position|Shift + Insert|

---

### 🧠 Remember This

> 🪄 Insertion Sort = “**Pick → Shift → Insert**”  
> It’s like arranging playing cards in your hand one by one.
