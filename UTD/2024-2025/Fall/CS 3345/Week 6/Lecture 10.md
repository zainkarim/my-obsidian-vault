# Trees (continued)
## BST `remove` Routine
- to safely delete from a BST while preserving its invariant, three cases need to be carefully designed
- if the node:
	- is a leaf node: immediately delete
	- has one child: delete and link the parent node to the child node
	- two child nodes:
## BST Complexities
- It can be proven that the average case complexity for BST operations is $\theta(\log n)$ -- why?
	- Think of a perfectly balanced BST
- Our goal is to reach worst case complexity: $O(\log n)$
- Complexity (traversal) is related to tree heigh $h$. In the worst case (skewed tree), $O(h)$ becomes $O(n)$.
- If we can ensure that the tree is balanced then we can get close to $O(\log n)$
## Balanced BST and Node Height
- TO achieved the desired complexity, we need to ensure that the BST is always balanced.
- Balanced BST can be checked by inspecting the height of the left subtree and right subtree of each node.
- Recall: node height is the length of the longest path from that node to a leaf.
## Calculating Node Heights
- The height of a node in a BST = the maximum height of it's children + 1.
## AVL Trees
- Adelson-Velsky and Landis tree is a self-balancing BST.
- Introduces an invariant to BST such that the heights of the two child subtrees of any node differ by at most one.
- $|h_l - h_r | \leq 1$
- If at any time they differ by more than one, rebalancing is done to restore this property.
- If we can prove that $h$ in such trees is $\log n$, then AVL tree operations (search, insert, delete) are all $O(\log n)$.
## AVL Complexity

#DSA #cs3345 #utd #CS #big-o #abstract-data-types #trees #binary-trees #binary-search-trees