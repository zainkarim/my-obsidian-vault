## How to measure Algorithm Efficiency
- By estimating the resources an algorithm needs to successfully complete, (time and space complexity)
- Goal is to evaluate different algorithms meant to solve a certain problem
- We can consider three ways to measure complexity:
	- Timing (time module to record time stamp) ❌
	- Counting operations ❌
	- Determine ==order of growth== (behavior of the algorithm) ✅
		- Evaluate the algorithm scalability in terms of input size.
		- Ignore small variations in implementation of algorithm.
## Order of Growth
- Express the growth of the program's runtime as a ==function== of the input size.
	- Trying to establish a ==mathematical relationship== between input size and program runtime.
- Expressed using ==Big O== notation, describes the worst case
	- Ex: O(n) means linear growth, which means the algorithm's performance scales with the size of the input.
#DSA #cs3345 #utd #CS #big-o 