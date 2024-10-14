# Hashing
## Hashing Function - Multiplication
- Multiple implementations
- $h(k) = [(a \times k) \mod 2^w] >> w-r$
	- $a$ is an odd constant, $w$ is the number of bits that represent integer $k$, and $m$ is $2^r$
	- This means that $r$-bits will produce a number from 0 to $m-1$
## Hashing Function - Universal
- Keys are not randomly distributed
- The goal of the universal hashing function is to produce random table indexes irrespective of keys.
- The idea is to select a hash function ==at random==
- Random hash function:
	- $h(k) = [(ak + b) \mod p] \mod m$
		- a and b are random numbers between {0, ... , p - 1}
		- p is a prime number greater than $|U|$
		- mod m at the end is to ensure that the number produced is between 0 and m - 1
### Example
- Assume m = 6 and p is chosen to b 17. a and b are randomly chosen to be 3 and 4 respectively
- $h_{a,b}(k) = [(ak + b) \mod p] \mod m$
- $h_{a,b}(8) = [(3 \times 8 + 4) \mod 17] \mod 6$
- $h_{a,b}(8) = [28 \mod 17] \mod 6 = 5$
## Hashing Function Problem
- Pigeonhole concept
	- More pigeons than holes
	- Causes collisions
		- Occurs when hash values of 2 distinct keys map to the same index in the array.
## Collisions
- For a given set of keys $K$:
	- if $|K| < m$, then collision may or may not happen, depending on the hashing function and key distribution
	- If $|K| > m$, then collisions will definitely happen
- Completely avoiding collision is very difficult
## Handling Collision
- Multiple collision handling approaches:
	- Chaining
	- Open addressing
		- Linear probing
		- Quadratic probing
		- Double Hashing
## Chaining
- Insert all elements that hash to the same slot into a linked list.
	- Linked List INSIDE of array element.
### Analysis
Worst case search scenario is when all keys hash to the same slot, so it ends up a linked list with $O(n)$
- The probability of this happening is $\frac{1}{m^n}$
- Expected length of the chain = $n/m$ (also known as load factor $\lambda$)
- AS long as m is $\Theta(n)$, then $\lambda$ is constant, and running time of search is $O(1 + \lambda)$. 1 is for the hashing time/
- It's important to choose the table size such that:
	- Small enough (less waste of space)
	- Typically 1/5 or 1/10 of total
	- Large enough (so that chains remain short)
## Open Addressing
- Attempt to find a contiguous empty cell to use as the key index
- Cell allocation follows the following formula
	- $h_i(x) = (hash(x) + f(i))\mod TableSize$, with $f(0) = 0$
	- $f$ is the collision resolution strategy (offset!)
- These tables (usually $\lambda < 0.5$) (room is twice the size of the number of students) are called probing hashing tables.

## Linear Probing
- $f$ is linear function of $i$, typically $f(i) = i$
	- Sequentially attempting to find an empty cell
	- Hash function: $h(k) = k \mod m$
	- 


#DSA #cs3345 #utd #CS #big-o  #hashing