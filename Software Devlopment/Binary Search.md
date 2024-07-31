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
#binary-search #CS #DSA #searching-algorithms 