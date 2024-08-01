- An iterative algorithm.
	- On each iteration, we want to ensure that the first $n^{th}$ items are in sorted order
		- On the $0^{th}$ iteration, we want to ensure that the first item in the list is sorted (it is)
		- On the $1^{th}$ iteration, we want to ensure that the first two items in the list are sorted
			- If the item in the 1 element is less than the item in the 0 element, then the item in the 1 element gets inserted into the 0 element, and the item in the 0 element becomes the item in the 1 element.
		- On the $2^{th}$ iteration, we want to ensure that the first three items in the list are sorted
			- If the item in the 2 element is less than the item in the 1 element but greater than the item in the 0 element, it will be inserted in between the two.
				- When an item is placed such that the item in the element before it is less than the item being placed, then we can guarantee that <i> every </i> item in a lower element than the item being placed has a lower value.
		- And so on


#DSA #CS #sorting-algorithms #insertion-sort