z# Compute Disk Structure & Performance
### File Storage
- Files can be stored using integral number of blocks
	- Blocks are the smallest unit able to store data

## Storing Large Trees
- Large search trees are rebuilt with as many child notes as can fit in a disk block to minimize disk access.
## M-Way Trees
- An M-ary (play on binary) tree node has up to $M$ child nodes
- Height of a complete M-ary tree is $\log_M n$
``` 
              A
           /  |  \
         B    C    D
       / | \  / | \  / | \
      E  F  G H  I  J K  L  M

```
- Recall, in a BInary try, the parent has. 1 key which is enouggh to determine the correct bath to one of the 2 child nodes
- Similarly, in a ternary tree, we need 2 keys.
- An M-way tree needs $M-1$ keys to guide the search to the next level.
## Storing Large Trees (Cont.)
- We have a large tree with $10^{9}$ items and the following:
	- 4-byte key
	- 4-byte pointers (to children)
	- 100 bytes of information
- We need to store this tree on a disk with the following specs:
	- Block size is 4kb
	- Disk seek time is 10ms
- Therefore, each block can be enough to store: $[ (4KB-4)/108) ]= 37$
- Each block can store 37 records with keys. Hence we can use a 38 way tree.
- Using a 38 way tree, a 4kb block would be partitioned as follows:
	- 37 records with their keys
	- 38 next pointers
	- 96 bytes unused
- Height of the 38-ary tree: $[\log_{38}(10^9)]$ = 5
- This means we will need 50ms at most in search time

- Can we do better?
	- Yes! We can separate pointers from keys and information
	- One idea is to store the information and keys in leaf nodes only and keep all internal nodes with pointers only. This can fit many more pointers, and hence more children and a shorter tree.
	- However, we still need to find a way to know which leaf to access
	- One idea is to store the smallest entries of all but the first sub-tree
	- Hence, we have 8 bytes (4 bytes for the pointers and 4 for the smallest key) for each subtree.
	- Therefore, 4KB can now fit 512 records in the internal nodes; i.e., we can use a 512-ary tree.
## B-Trees
- B-Trees use the previous idea but. with some additional restrictions
- It's an M-way Search Tree invariant which has strict balancing rules and will result in limiting the disk access.
- A B-Tree of order $M$ is an M-ary tree with the following properties:
	- The data items are stored at leaves
	- The non-leaf nodes store up to. $M-1$ keys to guide the searching
	- The root is either a leaf or has between two and $M$ children.
	- All non-leaf nodes (except for he root) have between $M/2$ and $M$ children.
	- All leaves are at the same depth and have between $L/2$ and $L$ data items.
- In the example and this structure, each leaf block can now store $(4KB-4)/104 = 39$ records (keys and information)
- Therefore, 10 billion records will require $\frac{10^9}{39} = 25,641,026$ leaf nodes (blocks).
- The tree's height is $\log_{512}25,641,026 = 2$
- Then the complete tree height is 3 (after adding the leaf node level)
- Assuming only root node is in memory, then any search would require three disk accesses, or 30ms.




#DSA #cs3345 #utd #CS #big-o #abstract-data-types #trees #binary-trees #binary-search-trees #m-way-trees #m-ary-trees #b-trees