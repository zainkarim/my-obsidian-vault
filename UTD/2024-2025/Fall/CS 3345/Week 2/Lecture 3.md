## Review: Max Subsequence Sum
### Algorithm 3: Divide and Conquer
Attempt to subdivide into two halves:
1. If cannot (base case), return cell value (maximum) if positive, zero if otherwise
2. Otherwise, attempt to subdivide the left half, then the right half
3. Find the max across the left and right
4. Select the max amongst left, right, or across

Example:

| 4   | -3  | 5   | -2  | -1  | 2   | 6   | -2  |
| --- | --- | --- | --- | --- | --- | --- | --- |


Complexity:
- The 2 for loop sequential blocks have a complexity of $O(n)$.
- Each of the two recursive calls need $T(N/2)$ to complete; total $2T(N/2)$
- So total time needed $T_{total} = 2T(N/2) + O(N)$ or $2T(N/2) + N$
	- $T(1 = 2^{0}) - 1$ ... Why?
	- $T(2 = 2^{1}) = 2T(1) + 2 = 4 = 2 * 2 = 2*(1+1 )$ 
	- $T(4 = 2^{2}) = 2T(2) + 4 = 12 = 4* 3 = 4*(2+1 )$ 
	- $T(8 = 2^{3}) = 2T(4) + 8 = 32 = 8* 4 = 8*(3+1 )$ 
==**So if $N = 2^{k}$, then $T(N) - N * (k+1) = N*log(N) = O(Nlog{N})$**==

### Can we make it better?
Look up ==**Kadane's Algorithm**==

## Abstract Data Types
- You can define your own data types.
- What is a data type?
	- Set of values and set of operations on these values
- Primitive data types are very efficient:
	- The values immediately map to machine representations
	- the operations immediately map to machine instructions
- The goal is to efficiently run programs that include other data types that are not built into he machine: complex numbers, colors, vectors, etc.
- An abstract data type os the tool we use to build non-primitive data types
- Representation is hidden from the client.
- Different representations of the same ADT will not make a difference to the client that is using it.
- To write a client to an ADT, you need to know:
	- ADT name (capitalized in Java: String)
	- How to construct new objects and associate variables to them
	- How to apply operations to a given object
### ADT Characteristics:
- Provides description of elements in terms of data types
- Defines relationship among individual elements
- Defines valid operations allowed on the elements, and parameters that can be passed.
- Specifies error conditions associated with the operations.