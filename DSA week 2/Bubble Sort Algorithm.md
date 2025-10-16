
****Bubble Sort**** is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is not suitable for large data sets as its average and worst-case time complexity are quite high.

- We sort the array using multiple passes. After the first pass, the maximum element goes to end (its correct position). Same way, after second pass, the second largest element goes to second last position and so on.
- In every pass, we process only those elements that have already not moved to correct position. After k passes, the largest k elements must have been moved to the last k positions.
- In a pass, we consider remaining elements and compare all adjacent and swap if larger element is before a smaller element. If we keep doing this, we get the largest (among the remaining elements) at its correct position.




## Complexity Analysis of Bubble Sort:

****Time Complexity:**** O(n2)  
****Auxiliary Space:**** O(1)  
Please refer [Complexity Analysis of Bubble Sort](https://www.geeksforgeeks.org/dsa/time-and-space-complexity-analysis-of-bubble-sort/) for details.

## ****Advantages of Bubble Sort:****

- Bubble sort is easy to understand and implement.
- It does not require any additional memory space.
- It is a stable sorting algorithm, meaning that elements with the same key value maintain their relative order in the sorted output.

## ****Disadvantages of Bubble Sort:****

- Bubble sort has a time complexity of O(n2) which makes it very slow for large data sets.
- Bubble sort has almost no or limited real world applications. It is mostly used in academics to teach different ways of sorting.


## ⚙️ Bubble Sort — Time Complexity Analysis

### 🧩 1. **Best Case**

- The array is already sorted.
    
- Only **one pass** of comparisons happens, and since no swaps occur → algorithm stops early (because of the optimized version).  
    ✅ **Best case:**
    

O(n)O(n)O(n)

👉 Because it only goes through `n` elements once (just checking).

---

### 🧩 2. **Average Case**

- The elements are in random order.
    
- It takes multiple passes before everything gets sorted.  
    ⚙️ Each pass makes fewer comparisons, but still roughly around `n²/2` operations.
    

✅ **Average case:**

O(n2)O(n^2)O(n2)

---

### 🧩 3. **Worst Case**

- The array is in **reverse order**.
    
- Every possible comparison and swap has to happen.
    

✅ **Worst case:**

O(n2)O(n^2)O(n2)

---

## 📊 Summary Table

|Case|Condition|Time Complexity|
|---|---|---|
|Best Case|Already sorted|✅ **O(n)** (optimized version)|
|Average Case|Random order|⚙️ **O(n²)**|
|Worst Case|Reverse order|❌ **O(n²)**|

---

## 🧠 Bonus: Space Complexity

Bubble Sort is an **in-place sorting algorithm**, so it doesn’t need extra arrays.  
✅ **Space Complexity = O(1)**

---

## 🎯 Final Answer (your version)

> “Yes, Bubble Sort has a best case of O(n) when optimized with a swap flag, and a worst case of O(n²).”

Perfectly correct ✅✅✅