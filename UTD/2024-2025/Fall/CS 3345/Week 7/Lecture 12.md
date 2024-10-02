## Another Look at Self-Balancing Trees
- AVL trees are great at providing self balancing once the tree goes out of balance (insert and delete)
	- Reminder: insertion works the same as a regular BST but is followed by checking if the tree is balanced.
- This can complicate insert and delete routines with the balancing algorithm
- Sometimes these balances become a burden or entirely unnecessary if the overall performance is acceptable with some degree of imbalance.
	- Additionally, this type of balancing requires additional storage overhead to augment the nodes with additional identifiers to help in the balancing routine.
		- Maintain the state of each node/
- All of this is to avoid making expensive searches to deep nodes.
	- What is these deep nodes are not searched as frequently?
## Splay Trees
- A somewhat balanced BST that maintains no state. and can perform as good as other BST strict self-balancing invariants.
	- Doesn't know if its balanced
- LAZY BST
	- At insert, splay trees will not immediately try to balance the tree as balanced trees do.
- Argument:
	- This is bad, if we don't try to balance immediately, then the price will be paid later down the line when you try to access deep nodes
- Answer:
	- True, but the splay tree will also USE the the expensive search to also balance the tree a little bit, so it will pay off.
### Burning Fat
- Why is search fast in a balanced BST?
	- Because the split of nodes in two subtrees are relatively close to one another.
- What if the search is slow?
	- One of the children is ==obese==
	- To solve this, the problem can be reframed as an opportunity
	- Exercise will burn fat, which "promotes" children that have potential.
	- This promotion is done through rotations
- Splay trees can then be described with the following key characteristics:
	- Insertion and deletion are the same as in the basic BST
	- Search time ranges from $O(\log n)$ to $O(n)$
	- Every found node as a result of the search is promoted through rotations to rhe root of the tree.
		- "If you search for a node, then that node is relevant. Bring it up to the root so that the next time you search for it, then you don't need to go deep to find it."
- As a result of each search and the associated rotations:
	- Tree structure improves toward a better balanced tree
	- Recent and more frequently accessed nodes will cluster toward the top of the tree
	- With $m$ searches ($m$ is relatively large), the tree will reach $O(\log n)$ amortized time bound
## Splay Tree Rotations
- The search procedure is composed of:
	- Search using the normal BST search routine
	- ==Splay== the found node to the root using double rotations +1 final single rotation if needed.
- The type of rotation is determined based on how the node $x$, its parent $y$ , and its grandparent $z$ are aligned together.
## Zig-Zig Rotation
1. Rotate grandparent and parent
2. Rotate node and parent
## Zig-Zag Rotation
1. Rotate node and parent
2. Rotate node and grandparent
==Exam practice: zig zig and zig zag==
## Practical Uses of Splay Tree
- Efficient for problems with frequent repetition of the same lookup (locality of reference)
	- Routing tables
	- memory caching and allocation
	- Data compression
## Compute Disk Structure & Performance


#DSA #cs3345 #utd #CS #big-o #abstract-data-types #trees #binary-trees #binary-search-trees #avl #splay-trees