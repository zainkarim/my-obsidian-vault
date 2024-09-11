## Stack ADT
- Special type of list
	- Insertion or deletion only happens from one end of the list (top) (LIFO) --> "last in first out"
	- `push` and `pop` are the method names for insert and delete
	- `pop` on an empty stack is considered an error in the stack ADT
	- An exceed stack maximum size is considered an implementation error
### Implementation
- No primitive data type (duh)
- ArrayList and LinkedList are both suitable for stack implementation
- LinkedList Implementation:
	- `push`:
		- $O(1)$
	- `pop`:
		- head.next() = head.next().next()
		- head.next().previous() = head
		- $O(1)$
- ArrayList Implementation:
	- `push` and `pop`: $O(1)$
### Stack Applications - Balancing Symbols
- To check for brace, bracket, and parenthesis correct balance in a program.
- Solution:
	- Initiate an empty stack
		- (Array) Set top of stack to -1
		- (LinkedList) Set head to point to tail or create new head and tail nodes and have them point to each other
	- Read file characters. For each read character:
		- If opening symbol, `push` to stack
		- If closing symbol, `pop` from the stack
			- If stack is empty, then give compilation error
			- If popped symbol is not matching, give compilation error.
			- If stack is not empty at the end of the program, give compilation error.
### ==Stack Applications - Postfix Expressions==
$5 + 5 \times 2 =$ `5 5 2 * +`
- Stack-based algorithm can convert infix to postfix and also evaluate postfix expressions.
- Example: $a + b \times c + (d \times e + f) \times g$
	- If an operand is parsed, print it as is
	- If an operator is parsed, then higher or equal priority operators are popped and printed, before this operator is pushed.
	- Open parens are pushed into the stack and CAN ONLY BE POPPED (but not printed) by closing one.
	- If no more operands, all remaining operators in the stack are popped.
	- Answer: `a b c * + d e * f + g * +`

## Queue ADT
- Special type of list
- push from one side, pop from the other, (FIFO)
- Basic operations:
	- `enqueue`: inserts an element at the end of the list (rear)
	- `dequeue`: removes (and returns) the element at the beginning of the list (called the front)
	- Array and LinkedList are both adequate ($O(1)$)
### Implementation
- To `enqueue` an element `x`
	- Increment `currentSize` and back pointer
	- Set `theArray[++back] = x`
- To `dequeue` an element:
	- Set the return value = `theArray[front++]`
	- Decrease `currentSize` and increment front
- ==Implement a mechanism to handle the situation when the queue is almost empty and yet back is indicating queue is full==
	- In the textbook: ==circular array==
#DSA #cs3345 #utd #CS #big-o #abstract-data-types #stack #queue
