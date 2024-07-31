## Selection Sort
1. Find the smallest item in the list and swap it to the 0th position.
2. Find the second smallest item in the list and switch it to the 1 position
3. Find the 3rd smallest element in the list and switch to the 2 position
4. ...
5. Stop when we have swapped the second largest item into the second to last position
``` python
def selection_sort(list):
	for i in range(0, len(list) - 1):
		min_index = i
		min_val = list[i]
		for j in range(i + 1, len(list)):
			if list[j] < min_val:
				min_val = list[j]
				min_index = j
		temp = list[i]
		list[i] = min value
		liost[min_index] = temp
```
#DSA #CS #sorting-algorithms #selection-sort
