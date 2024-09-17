# Trees
Still a list with nodes, but theres a variation in structure
- Composed of nodes
	- Each node has at least one parent and - or more child nodes
- ==Can reduce the expensive $O(n)$ access time of the linked list to $O(\log n)$==
	- Ex: $\log 1000000000 = 30$ 
## Definitions and Key Terms
- A collection of $N$ nodes will have $N-1$ edges.
- Path from node $n_1$ to $n_k$ is the sequence of nodes $n_1, n_2, \ldots , n_k$ such that $n_i$ is parent of $n_{i + 1}$, $1 \leq i \leq k$
- Length of path = number of edges = $k-1$
	- Depth: length of the path from the root to $n_i$
	- Height: length of the longest path from $n_i$ to a leaf
## Implementation
Each node can have an arbitrary number of children
1. define `firstChild` and `nextSibling`
## DS Invariants and Binary Trees
- ==Invariants are rules for a data structure or algorithm==
	- Certain characteristics or conditions that are always true
- Binary Trees:
	- ==Special trees that can only have 2 child nodes==
## Binary Tree Structure
- Similar to a doubly linked list
```java
public class Node<K> {
	K data;
	Node<K> left;
	Node<K> right;
}
```
- Max number of leaves: $2^h$
- Min number of leaves: $1$
- Min number of nodes: $h + 1$
## Binary Tree Maximum Number of Nodes
The max number of nodes is $2^{h+1} - 1$
**Proof by induction:**
- Assumption: a tree of height $h$ has max node = $2^{h+1}-1$
- **Base case:** $h=0$ (one node) $= 2^{0+1} - 1 = 1$
- Proof a tree of height $h + 1$ has max node $= 2^{(h+1)+1}-1 = 2^{h+2} - 1$
- For height of $h+1$, total nodes $=(2^{h+1} - 1) + (2^{h+1} - 1) = 2^{h+2} - 1$
## Special binary tree types
| Full                                                | Complete                                                                                                                             | Perfect                                                                             | Skewed                     |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- | -------------------------- |
| Nodes can have either 0 or two child nodes          | Has all levels completely filled with nodes except the last level. In the last level, all of the nodes are as left side as possible. | All internal nodes have 2 children, and all leaf nodes are at the same depth/level. | Every parent node has onlh |
| Number of leaf nodes = Number of internal nodes + 1 | ==Binary Heap== is an important use case of Complete Binary Trees                                                                    | The total number of nodes in a perfect binary tree with height h is $2^{h+1} - 1$   |                            |
|                                                     |                                                                                                                                      |                                                                                     |                            |
## Binary Tree Traversals
- Tree traversals can be broadly categorized into two main groups:
  1. Depth-First Search (DFS)
  2. Breadth-First Search (BFS)

DFS algorithms have three variants:
- Preorder Traversal (current-left-right)
- In Order Traversal (left-current-right)
- Postorder Traversal (left-right-current)
### Inorder
- Most used variant of DFS Traversal of the tree
- Recursive
	- go to left subtree
	- visit ode
	- go to right subtree
- 


#DSA #cs3345 #utd #CS #big-o #abstract-data-types #trees #binary-trees #depth-first-search #breadth-first-search #DFS #BFS