# Hashing
## Search Speed
- In an unsorted data set, $O(n)$ search time
- In a balanced BST, it is reduced to $O(\log n)$
- Can we do better? $O(1)$?
- We can achieve this with Hash Tables!
==Think of the idea of matching the data element keys to an array index.==
**Example:** Storing names in an array with ID numbers(keys) as array index.
## Key - Direct Access Table
- ID numbers range is 2000000001 to 2021999999
- Each record is an object containing info

| Index     | Student Info    |
| --------- | --------------- |
| 0         |                 |
| 1         |                 |
| ...       |                 |
| ...       |                 |
| 200000001 |                 |
| 200000002 | Student Info  1 |
| 200000003 |                 |
| ...       | ...             | 
|           | Student info 2  |

- Search(K) = Array[K]
	- Key becomes the index in the array
- This means $O(1)$. Is there an issue here?
- The issue is that there's a lot of waste!
- Also, what if the key is not a positive integer?

Hashing builds on this idea while solving the above problem!

## What is Hashing?
A Hash Map is a data structure that maps a data element key to a specific array index (and stores that element at that array cell).
Mapping happens through function that chops, slices, and dices the key and produces a hash code that corresponds to ...
## Dictionaries
- Hashing is an implementation of the dictionary data structure
- Data structure representing a set of elements, with insertion, deletion, and tests for membership
- One of the most popular data structures in CS
	- In Java, Dictionary is an abstract class that can be implemented by different classes including `HashTables`, `HashMap`, `LinkedHashMap`, etc.
- Methods:
	- Insert (item)
	- Delete (item)
	- Search (key): returns item with given key if found (exact search)
## Uses of Dictionaries
- Database
- Spell check
	- Advanced spell check will provide suggestions
- Compilers and interpreters
- Network routers and computer ports
- More specialty use:
	- Substring search
## Hashing Approach
- Recall direct-indexing problems:
- 1. A lot of wasted space
	- Solved using hashing
- 2. Non-integer keys
	- Solved through pre-hashing
	- Process where a non-positive integer key is changed into a positive-integer key
	- Ideally, per-hash(x) = pre-hash(y) only if x = y. Unfortunately, this is not the case all of the time.
## Reducing Space by Hashing
- The idea is to reduce the universe ($U$) of all keys down to a reasonable size $m$ (table size), and each key is mapped to a specific index in the array.
- Hashing uses the NUMBER OF KEYS
- Objective: $m = \Theta(n)$, where $n$ is the number of keys in the dictionary
- How do we build $h$ (the hashing function)?
## Hashing Function
Recall, we want $m = \Theta(n)$
- Hash function transforms a key into a table address
- A good hash function should:
	- Be easy to compute
	- Approximates a random function: for every input, every output is equally likely (simple uniform hashing)
		- Ex: Pr(getting a 1 when rolling a die) = Pr(rolling a 2) = Pr(rolling a 3) = $\frac{1}{6}$
- In practice, it is very hard to satisfy the simple uniform hashing property unless we know in advance the probability distribution that keys are drawn from.
- There are many different hashing functions
	- Addition
	- Multiplication
	- Universal hashing
	- Polynomial
## Hashing Function: Division
- Hash a key into one of the $m$ slots in the hash table by taking the remainder of $k \div m$
- $h(k) = k\mod m$
	- Key is guaranteed to be between $0$ and $m-1$
- Advantage: simple and fast
- Disadvantages:
	- Bad selection of $m$ (table size) can cause a lot of ==collisions== (hashing function produces the same index for more than one key)
	- Ex: Powers of 2, 10, and non-prime numbers in general
	- Ex: if $m$ is even and the majority of the keys are also even, it will result in a half full hash table.
- In general, this method is okay if $m$ is prime and not too close to any power of 2 or 10
## Hashing Function: Division Example
- If $m = 2^p$, then $h(k)$ is just the least significant $p$ of the binary representation of $k$.