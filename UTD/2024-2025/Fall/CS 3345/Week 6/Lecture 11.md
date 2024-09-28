## Review AVL Trees
- Self balancing
- Has the height of the two child subtrees at any node differ by at most one.
	- If they ever differ by more than one, rebalancing is done
- AVL tree operations are all $O(\log n)$
- `insert` and `delete` methods could potentially cause imbalance in the AVL tree.
## AVL Complexity Review
- Worst case (balanced) is when. the height of thge right subtree is 1 more than the left _every node_ (or vice versa).
- Within the same height, what would adding any additional node to to the tree balance?
	- It would make it more balanced
- $N_h$
	- $N_0 = 1$
	- $N_1 = 1 + N_{h-1} + N_{h-2}$
- Resembles Fibonacci! (almost), bigger by 1
	- $N_h > F_h$
	- $N_h > F_h = \frac{\phi^h}{\sqrt(5)}$
		- $\phi = \frac{a + b}{a} = \frac{a}{b} \approx 1.618$
	- $\frac{\phi^h}{\sqrt(5)} < n$ yields $h < \log_\phi n + C$
## AVL `insert` Routine
- Similar to insert routine in BST but with one extra step
- `insert`:
	- Insert node in the proper subtree using the simple BST insert
	- Balance the tree
- Balancing AVL trees happens through ==rotation==.
- Depending on where imbalance occurs, one or double rotations might be needed to balance the tree.
## AVL Imbalance Cases
- Consider the following four imbalance cases at node $\alpha$ caused by the insertion of a new node.

| 1. Left subtree of a left child   | 2. Right subtree of a left child  | 3. Left subtree of a right child | 4. Right subtree of a right child |
| --------------------------------- | --------------------------------- | -------------------------------- | --------------------------------- |
| Can be fixed with single rotation | Can be fixed with double rotation | Can be fixed with                | Can be fixed with single rotation |
|                                   |                                   |                                  |                                   |
## Single rotation - Case 1
Left of left
- Single rotation can be easily accomplished by some link changes between nodes.
- "You are being demoted and your deputy is being promoted"
## Double rotation - Case 2 and 3
Cases 2 & 3 cannot be solved by a single rotation,  because it simply replaces the parent node but does NOT change the depth.
- Double rotation
## Single rotation - Case 4
Mirror of case 1
## Node Augmentation
- The height of each node is essential to determine if an AVL tree is balanced or not
- This could be implemented using an int, or possibly a simple indicator such as +1, 0, -1.
## AVL insert routine
- The `insert` routine is the exact same as the BST, but it adds one line of code at the end of the routine: `return balance(r);`
- `balance(AvlNode t) method:
	- Determines if single or double rotation is needed and invokes the appropriate rotation method.`


#DSA #cs3345 #utd #CS #big-o #abstract-data-types #trees #binary-trees #binary-search-trees #avl