## Binary Heap Basic Operations - `insert`
- To insert element `x` into a heap: throw it at the end and bubble (percolate) it up
	- add a child in the next available location that preserves the complete binary tree invariant
	- "bubble" the node with its parent as needed to preserve the heap order invariant
- Try the code!
## Binary Heap Basic Operations - `deleteMin`
- To delete the min element `x` (the root) from the heap
	- replace the root key with the key of that tree leaf node, and remove that leaf node
	- push the key down (as needed) by replacing it with the smaller child value
- ==Try the code!==
## Binary Heap Operations Use & Complexity
- Insertion: Worst case is $O(\log n)$, average is $O(1)$
- Deletion: Worst case is $O(\log n)$, average is $O(\log n)$
- Search: Worst case is $O(n)$
- Use a hash map to store the node locations is the heap
	- ==Try this at home!==
## Other Operations
- Since the access of any key is $O(1)$, we can use the location of a node in defining the following methods that all perform within $O(\log n)$
- `decreaseKey`(p, $\Delta$): 
- `decreaseKey`(p, $\Delta$): 
- `delete(p)`: removes the node at position $p$ from the heap
	- find key, decrease key by a large number, goes to the top, deleteMin
