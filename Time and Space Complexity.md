
<h5>Complexity in computer science refers to the resources an algorithm consumes.</h5>



<h4>Time ComplexityWhat it is:  </h4>

The amount of time an algorithm takes to complete as a function of the length of the input.

<h4> What it measures: </h4>The number of operations (like comparisons, additions, assignments) the algorithm performs, not the actual elapsed time (which can vary based on the computer's speed, programming language, etc.).

<h4> Goal: </h4> 
To estimate how the running time grows as the input size (n) increases.

<h4> Space ComplexityWhat it is: </h4>

The amount of memory (space) an algorithm uses as a function of the length of the input.What it measures: The extra storage space required by the algorithm (e.g., memory needed for variables, arrays, or recursive calls), excluding the space used for the input itself.⚙️ 

<h4> Big O Notation</h4>

Big O notation (O) is the most common way to express the upper bound of an algorithm's running time (or space) complexity. It describes the worst-case scenario or the asymptotic behavior—how the algorithm scales when the input (n) becomes very large.It simplifies the analysis by ignoring constant factors and lower-order terms, focusing on the term that grows the fastest

.<h4>Example: </h4>

Finding an element in a listConsider searching for a number in an unsorted list of n elements.

<h4>Best Case: </h4>

The number is the first element. It takes just 1 operation. This is O(1).

<h4> Worst Case: </h4>

The number is the last element or isn't in the list. You check all n elements. It takes n operations. This is O(n).

<h4> Big O Focus: </h4>

We use Big O to describe the Worst Case because that gives us a guaranteed upper limit on the performance. So, the search is typically described as O(n).Mathematical Deep Dive (Simplified)If an algorithm's running time is calculated as T(n)=3n 2 +5n+10.Drop Lower Order 

<h4> Terms: </h4> 

As n gets huge, n 2 grows much faster than 5n or 10. We ignore them: 3n 2 .Drop Constant Factors:

The coefficient 3 is a constant. We ignore it: n 2 .Big O: The complexity is O(n 2 ).
