Generally speaking, there are two types of arrays:
- Static Arrays
- Dynamic Arrays
# Static Arrays
An array is stored as a contiguous block of data in RAM.
The two most common array operations are:
- Reading data
- Writing data
## Reading Data
We can access values in an array by referencing the index a value resides at in memory.
To read a value, assuming we have the index, is an instant operation. This is happening at **<u>constant time</u>**. Therefore, the time complexity is $O(1)$. See [[Big O Cheat Sheet]] for more info on runtime complexity.
## Writing Data
Writing to the last empty element of a static array is also an instant operation. Therefore, the time complexity is also $O(1)$. Similarly, removing a value is also an operation with $O(1)$ complexity.
### Arbitrarily inserting variables in arrays
Take a look at this array:

| 5 | 6 |  |
| - | - | - |
What if you wanted to arbitrarily insert a value into the middle of the array (between 5 and 6) or at the beginning of the array before (5). For example, what if you wanted the array to look like this?

| 4   | 5   | 6   | 
| --- | --- | --- |

We could add the 4 to the end of the array, but that does not yield the desired outcome. **<u>The order of the elements inside of an array matters</u>** because the values in an array are stored in a contiguous block of memory.

To carry out this task, we:
1. Move the 6 to the next index

| 5   |     | 6   |
| --- | --- | --- |

2. Move the 5 to the next index
   
|     | 5   | 6   |
| --- | --- | --- |

3. Insert the 4 at index 0.

| 4   | 5   | 6   |
| --- | --- | --- |

The downside of this is that we couldn't complete this task in a single operation. In the worst case, if we have $n$ elements (the length of the array) and we want to add one more to the beginning of the array, then we need to move those $n$ elements $n$ times, resulting in $n$ number of operations. This is a time complexity of $O(n)$.
### Arbitrarily removing variables in arrays
The same is true if we arbitrarily remove a value in an array.

| 5   | 6   | 7   |
| --- | --- | --- |

If we wanted to get rid of the first element, then we would have to move each element to the $i-1$ index.

| 6   | 7   |     | 
| --- | --- | --- |

This is a time complexity of $O(n)$.
# Dynamic Arrays
Dynamic arrays are much more common and useful than static arrays. In python and javascript, dynamic arrays are the default. 
Recall that the problem at hand is the fixed size problem. Unlike static arrays, you don't have to specify a dynamic array's size.
## Writing Data
Consider the following array:

| 0   | 4   |     |
| --- | --- | --- |

Pushing a 7 to the end of the array has an $O(1)$ time complexity.

| 0   | 4   |    7 |
| --- | --- | --- |

What would happen if we tried to append a 9 to the end of the array? In a static array, we have the issue of the data being stored in a contiguous block of memory. However, in a dynamic array, a <i>different</i> block of memory twice the size of the previous block of memory is allocated, and the data from the previous memory block is moved to the new memory block.

| 0   | 4   | 7   | 9   |     |     |
| --- | --- | --- | --- | --- | --- |

Once the new array is created, the previous array is deallocated in memory.

This process has an $O(n)$ runtime complexity, where $n$ is the length of the array.

However, the vast majority of times we push data to an array, there will already be memory available to be allocated, hence giving us an $O(1)$ runtime. Therefore, the <i>average</i> time complexity of this process is $O(1)$. This is known as **<u>amortized time complexity</u>**.

#arrays #DSA #CS

