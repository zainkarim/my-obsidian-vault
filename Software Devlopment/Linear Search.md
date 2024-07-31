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

#linear-search #CS #DSA #searching-algorithms 