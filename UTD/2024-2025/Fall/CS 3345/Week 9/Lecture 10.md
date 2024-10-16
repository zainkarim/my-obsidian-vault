# Priority Queues (Heaps)
- Ques (FIFO)
- Sometimes, violating the strict FIFO model can be desirable
- Priority queue: serving the keys based on priority.
- Abstract data type
## Array Representation of Binary Trees
- Store a binary tree structure in an array.
	- Gives advantage of fast access.
	- Requires a simple algorithm to store the keys and the relationship between them (parent-child relationship)
	- Store elements using breadth first search algorithm (by layer)
		- If an element is at cell $i$:
			- Left child is at cell $2 \times i$
			- Right child is at $2 \times i + 1$
		- Any key at cell $i$ will have its parent found at cell $[i / 2]$
| -   | a   | b   | c   | d   | e   | f   | g   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   |
## Complete Binary Trees
- Binary trees with all levels completely filled, with the exception of the last level. In the last level, the nodes are as far on the left side as possible.
- Height of the complete binary tree is $[\log n]$
## Binary Heap:
- Implementation of priority queue
- Is a binary tree with 2 properties:
	- 1. Structure:
		- A heap is a COMPLETE binary tree
	- 2. Order of data
		- Min-Heap: For every node X, the key in the parent of X is smalelr (or equal) the key in X (with the exception of the root).
	- 