## Review: Order of Growth
- Goal is to evaluate input performance when input is very large
- express growth of the runtime as a function of input size
- determine upper bound on growth (Big O)
## Complexity Classes
$O(1)$ denotes ==constant running time==
$O(\log{n})$ denotes logarithmic running time
$O(n)$ denotes linear running time (worse than log)
$O(n\log{n})$ denotes log-linear running time
$O(n^c)$ denotes a polynomial running time
$O(c^n)$ denotes a exponential running time (worse overall)
## Important Rules
- O() rule of addition:
	- Used for sequential statements
	- $O(f(n)) + O(g(n) = O(f(n) + g(n))$
	- Ex: $O(n) + O(n^2) = (O(n + n^2) = O(n^2)$
- Rule of multiplication
	- Used for nested statements
	- $O(f(n)) *+* O(g(n) = O(f(n) *+* g(n))$
	- Ex: for loop nested in another for loop
		- $O(n) * O(n) = O(n^2)$
## Study: Maximum Subsequence Sum
Given integers $A_1, A_2, ... , A_n$, find the sequence of the absolute value of the following:
	$\sum_{k=1}^{j} A_k$ and $1 \leq i, j \leq N$
### Algorithm
1. Do exhaustive trials of all possible sequences and return the one that produces the highest number.
	$O(n^c)$
#### Recursion Review
An object is recursive if:
- part of the object refers to the entire object
- one part of the object refers to another and vice versa (mutual)
Recursion must satisfy 2 conditions:
1. Base case (exit strategy): return without making a recursion
2. Progression: change state and move towards the base case
Example: factorial
```java
public static long fac(long n) {
	if(n <= 1)
		return 1;
	else
		return n * fac(n - 1);
}
```
#### Is recursion always recommended?
If an iterative solution exists for a numerical problem then it is preferred over a recursive solution as recursion is more expensive.
### Back to Maximum Subsequence Sum Algorithm:
2. Divide and Conquer:
	Think of the idea to divide the array into 2 subarrays; where will the maximum subsequence be?
	Either the left subarray, right subarray, or across
	1. Algorithm recursively subdivides the array and 
#DSA #cs3345 #utd #CS #big-o 