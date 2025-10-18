### 🔹 **Definition**

Selection Sort is a simple **comparison-based sorting algorithm** that divides the array into two parts:

- **Sorted subarray** (at the beginning)
    
- **Unsorted subarray** (remaining part)
    

It repeatedly selects the **smallest (or largest)** element from the **unsorted** part and places it at the **end of the sorted** part.

---

### 🔹 **Algorithm Steps**

1. Start with the first element (assume it’s the smallest).
    
2. Compare it with all remaining elements.
    
3. If you find a smaller element, mark its index.
    
4. After the inner loop finishes, **swap** the smallest element found with the current element.
    
5. Expand the sorted region by 1 and **repeat**.
    

---

### 🔹 **Code Example (Ascending Order)**

`function selectionSort(arr) { 

for (let i = 0; i < arr.length - 1; i++) {      

let minIndex = i;      

for (let j = i + 1; j < arr.length; j++) {         

if (arr[j] < arr[minIndex]) {         

minIndex = j;             }     

}     

if (minIndex !== i) {    

[arr[i], arr[minIndex]] = [arr[minIndex], arr[i]]; // Swap         }     

}     return arr; 

} 

console.log(selectionSort([29, 10, 14, 37, 13]));`

**Output:**  
`[10, 13, 14, 29, 37]`

---

### 🔹 **Step-by-Step Flow**

Initial array:  
`[29, 10, 14, 37, 13]`

|Pass|Sorted Subarray|Unsorted Subarray|Action|
|---|---|---|---|
|1|`[]`|`[29, 10, 14, 37, 13]`|Find min = 10 → swap with 29|
|2|`[10]`|`[29, 14, 37, 13]`|Find min = 13 → swap with 29|
|3|`[10, 13]`|`[14, 37, 29]`|Find min = 14 → already in place|
|4|`[10, 13, 14]`|`[37, 29]`|Find min = 29 → swap with 37|
|5|`[10, 13, 14, 29, 37]`|`[]`|Sorted ✅|

---

### 🔹 **Time Complexity**

|Case|Complexity|Explanation|
|---|---|---|
|**Best**|O(n²)|Even if already sorted, still compares all pairs|
|**Average**|O(n²)|Typical comparisons|
|**Worst**|O(n²)|Reverse sorted array|
|**Space**|O(1)|In-place (no extra memory)|

---

### 🔹 **Key Notes**

- Simple but **not efficient** for large arrays.
    
- **Swaps fewer times** than bubble sort (better for small memory operations).
    
- **Unstable** (equal elements may change order).
    
- **Good for small datasets or learning sorting logic.**
    

---

### 🧩 **Sorted vs Unsorted Regions (Visualization)**

At each pass:

`Pass 1: [S] [] → [10] [29,14,37,13] Pass 2: [S] [10] → [10,13] [14,37,29] Pass 3: [S] [10,13] → [10,13,14] [37,29] Pass 4: [S] [10,13,14] → [10,13,14,29] [37] Pass 5: [S] [10,13,14,29,37] ✅`

🟩 **Green** (sorted) part grows each time  
🟥 **Red** (unsorted) part shrinks each time