## Review: ADTs
[Lecture 3]
- ADT is the tool we use to build non-primitive data types
- Representation is hidden from the client
- Different representations will not make a difference to the client
- ==Container as well as operations ==
### ADT Characteristics
- Provides description of elements in terms of data types
- defines relationship among individual elements
- defines valid operations allowed on the elements, and parameters that can be passed
- ==Specifies error conditions associated in the operations==
	- How would you handle the case in which the user misuses the INTERFACE?

## The List
- will be used in many algorithms
- General form: $$A_0, A_1, A_2, \ldots , A_{n-1}$$
	- List has size of $n$, and the special list of size $0$ is an empty list.
	- $A_i$ follows $A_{i-1}$ $(i < n)$ and $A_{i-1}$ precedes $A_i$  $(i > 0)$
	- position of element  $A_i$ is $i$.
- Key operations:
	- `printList`
	- `makeEmpty` 
	- `find`
	- `insert`
	- `remove`
	- `findKth`
	- merge, compare, divide in half, and more.
	- etc.
- Two implementations of Lists:
	1. Array
	2. Linked List
1. Array Implementation
	- Max list size must be estimated because arrays are created with fixed capacity
	- Can be solved in the implementation by moving the elements in the array into a larger array.
	- `findKth`: $O(1)$ ✅
	- `printList`: $O(n)$ ✅
	- `insert`: expensive, requires unnecessary $O(n)$ ❌
	- `remove`: expensive, requires unnecessary $O(n)$ ❌
1. Linked List Implementation
	- Solves the expensive cost of insert and delete
	- Consists of a series of nodes which may or may not be adjacent in memory,. Each node consists of two parts:
		1. Element value
		2. Link to a node containing its successor (called the ==next link==)
	- The next link in the last node references `null`.
	- `printList`: $O(n)$ ✅
	- `findKth`: $O(n)$ ❌
	- `insert` and `remove` has complexity $O(1)$ ✅
		- However, if you have to get there, it's $O(n)$
		- To handle the const of adding or deleting to the end of the list, we have to add one more Link to each node to point to its predecessor.

## Java Collections API
- Includes implementation of common data structures (`java.util` package)
- Notion of collection means the storage of identically typed objects
- The Collections API includes implementations of the List ADT
- The collection is abstracted in the Collection Interface
- https://docs.oracle.com/javase/8/docs/technotes/guides/collecyions/overview.html
## Java Collection Interface
```java
java.util.Iterator<AnyType> iterator();
```
## Traversing Consistency
- Need a consistent way to traverse elements in any collection implementation
## Iterator
- Collections that implement the iterable interface must include a method called iterator, which returns an object of type `Iterator`.
- The Iterator is an interface defined in package java.util
``` java
public interface Iterator<AnyType> {
	boolean hasNext();
	AnyType next();
	void remove();
}
```

#DSA #cs3345 #utd #CS #big-o  #abstract-data-types
