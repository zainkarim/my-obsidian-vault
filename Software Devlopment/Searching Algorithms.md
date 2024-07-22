# Searching
Given a list containing $n$ items, find a defined value

## Random Search
Pick a random location in the list and check it against the key. If item not found, try again.
- best-case: 1
- worse-case: infinite
## Linear Search
Iterates through list containing $n$ items until key is found
```python
def linear_search(list, key):
	index = 0
	while index < len(list):
		if key == list[index]:
			return index
		else:
			index += 1
	return None
```
- best-case: 1
- worst-case: $n$
## Binary Search
1. Go to the middle of a ___sorted___ list and check if that element contains the key.
2. If not and the key is ___less than___ the value in the middle element, then we know that it's in the left hand side of the list. If the key is ___greater___ than the middle element, then we know that it's in the right hand side of the list.
3. Go to the middle of the side of the list that the key should be located in
4. Repeat until the key is found
- best-case: 1
- worse-case: $log_{2}(n)+1$

| length of list | comparisons |
| -------------- | ----------- |
| 2              | 2           |
| 4              | 3           |
| 8              | 4           |
| 16             | 5           |
| 32             | 6           |
| $n$             | $log_{2}(n) + 1$ |

#DSA #CS #searching-algorithms
