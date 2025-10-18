
### **1️⃣ Concept**

- Quick Sort = **Divide & Conquer** algorithm
    
- Steps:
    
    1. Pick a **pivot element** from the array (commonly last element)
        
    2. Partition the array into:
        
        - **Left** → elements smaller than pivot
            
        - **Right** → elements greater than or equal to pivot
            
    3. Recursively sort **left** and **right** arrays
        
    4. Combine → `[...quick(left), pivot, ...quick(right)]`
        
- **Time Complexity:**
    
    - Best / Average: **O(n log n)**
        
    - Worst: **O(n²)** (if pivot is always largest/smallest)
        
- **Space Complexity:** O(n) due to recursion + array slices
    

---

### **2️⃣ Quick Sort in JS (Template)**

`function quickSort(arr) {  

// Base case: 0 or 1 element is already sorted   
if (arr.length <= 1) return arr;     

// Step 1: Pick pivot (last element)   
const pivot = arr[arr.length - 1];   

let left = [];     let right = [];   

// Step 2: Partition (exclude pivot)    

for (let i = 0; i < arr.length - 1; i++) { 

if (arr[i] < pivot) left.push(arr[i]);     

else right.push(arr[i]);     }      

// Step 3: Recursively sort left and right, combine

return [...quickSort(left), pivot, ...quickSort(right)]; }  

// Example: console.log(quickSort([5,3,8,4,2,7,1]));

// Output: [1,2,3,4,5,7,8]`

---

### **3️⃣ Key Notes**

1. **Base Case:** Always check `arr.length <= 1` to stop recursion.
    
2. **Exclude pivot** from the partition loop to avoid infinite recursion.
    
3. **Duplicates:** Duplicates go into **right** or **left** consistently.
    
4. **Descending Sort:** Change `if (arr[i] < pivot)` → `if (arr[i] > pivot)`
    
5. **Memory:** Uses extra space due to slices; in-place Quick Sort is faster but more complex.