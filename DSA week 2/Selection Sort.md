
****Selection Sort**** is a comparison-based sorting algorithm. It sorts an array by repeatedly selecting the ****smallest (or largest)**** element from the unsorted portion and swapping it with the first unsorted element. This process continues until the entire array is sorted.

1. First we find the smallest element and swap it with the first element. This way we get the smallest element at its correct position.
2. Then we find the smallest among remaining elements (or second smallest) and swap it with the second element.
3. We keep doing this until we get all elements moved to correct position.
## Complexity Analysis of Selection Sort

****Time Complexity: O(n********2********)**** ,as there are two nested loops:

- One loop to select an element of Array one by one = O(n)
- Another loop to compare that element with every other Array element = O(n)
- Therefore overall complexity = O(n) * O(n) = O(n*n) = O(n2)

****Auxiliary Space:**** O(1) as the only extra memory used is for temporary variables.

## Advantages of Selection Sort

- Easy to understand and implement, making it ideal for teaching basic sorting concepts.
- Requires only a constant O(1) extra memory space.
- It requires less number of swaps (or memory writes) compared to many other standard algorithms. Only [cycle sort](https://www.geeksforgeeks.org/dsa/cycle-sort/) beats it in terms of memory writes. Therefore it can be simple algorithm choice when memory writes are costly.

## ****Disadvantages of the Selection Sort****

- Selection sort has a time complexity of O(n^2) makes it slower compared to algorithms like [Quick Sort](https://www.geeksforgeeks.org/dsa/quick-sort-algorithm/) or [Merge Sort](https://www.geeksforgeeks.org/dsa/merge-sort/).
- Does not maintain the relative order of equal elements which means it is not stable.

## Applications of Selection Sort

- Perfect for teaching fundamental sorting mechanisms and algorithm design.
- Suitable for small lists where the overhead of more complex algorithms isn't justified and memory writing is costly as it requires less memory writes compared to other standard sorting algorithms.
- [Heap Sort](https://www.geeksforgeeks.org/dsa/heap-sort/) algorithm is based on Selection Sort.