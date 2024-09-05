## Review
- Collection API
	- Queues, lists, etc
- ADT
	- Link between interface and implementation
- Iterators
	- returns an object of type iterator
	- the Iterator is an interfaced in `java.util`
```java
public interface Iterator<AnyType> {
	boolean hasNExt();
	AnyType next();
	void remove();
}
```

==The collection adds the element at the very end. It does not need an index.==
```java
import java.util.ArrayList;
import java.util.Iterator;

ArrayList<Integer>list = new ArrayList<Integer>();
list.add(15);
list.add(22);
list.add(19);
list.add(99);

Iterator here = list.iterator();

System.out.println(here.next());
```

| 15  | 22  | 19  | 99  |
| --- | --- | --- | --- |

- The List Interface
``` java
public interface List<AnyType> extends Collection<AnyType> {
	AnyType get(int idx); // returns element value at idx pos
	AnyType set(int idx, AnyType newVal); // sets element at idx position to newVal
	void add (int idx, AnyType x); // Places new item x at idx
	void remove (int idx); // removes item at position idx
	
	ListIterator<AnyType> listIterator(int pos);
}
```

## ArrayList vs LinkedList

- ArrayList
	- `get` and `set` are of constant complexity $O(1)$
	- `add` and `remove` are expensive ($O(n)$)
- LinkedList
	- `add` and `remove` can be cheap if position is close to a known pointer
	- provides `addFirst`, `removeFirst`, etc. for better performance.
	- `get` and `set` are expensive unless near the end of the linked list.
```java
public static void makeList1(List<Integer>lst, int N) {
	lst.clear()
	for(int i = 0; i < n; i++)
		lst.add(i);
}
```
- Running time is $O(n)$ for both ArrayList and LinkedList implementations
	- Completing an $O(1)$ operation $n$ times.
```java
public static void makeList2(List<Integer>lst, int N) {
	lst.clear()
	for(int i = 0; i < n; i++)
		lst.add(0, i);
}
```
- LinkedList will take $O(n)$, while ArrayList will take $O(n^2)$
```java
public static int sum(List<Integer>lst) {
	int total = 0;
	for(int i = 0; i < n; i++) {
		total += lst.get(i);
	}
}
```
- LinkedList will take $O(n^2)$, while ArrayList will take $O(n)$
	- For the LinkedList, each `get` call traverses from the beginning
	- Using an ==enhanced for loop== will make the runtime $O(n)$
```java
public static <AnyType> void print(Collection<AnyType> coll) {
	for(AnyType item : coll) {
		System.out.println(item);
	}
}
```
- The enhanced for loop is built using the Iterator methods
```java
for(Iterator<AnyType> i = coll.iterator(); i.hasNext())
	AnyType item = i.next();
```
## Example
- We need to remove all even numbers from a list. For example, if the list is 6, 5, 1, 4, 2, then after the routine run, the list will be 5, 1
	- We need to think of a solution other than creating a new List.
```java
public static void removeEvensVer1(List<integer> lst) {
	int i = 0;
	while(i < lst.size()) // O(n)
		if(lst.get(1) % 2 == 0) // O(1) for ArrayList,
								// O(n) for LinkedList
			lst.remove(1); // O(n) for ArrayList,
						   // O(1) for LinkedList
		else
			i++
}
```
## Example 2
- We need to remove all even numbers from a list. For example, if the list is 6, 5, 1, 4, 2, then after the routine run, the list will be 5, 1
	- We need to think of a solution other than creating a new List.
```java
public static void removeEvensVer2(List<integer> lst) {
	Iterator<Integer> itr = lst.interator();
	while(itr.hasNext()) // O(n)
		if(itr.next() % 2 == 0)
			itr.remove();
}
```
- $O(n^2)$ for `ArrayList`, $O(n)$ for `LinkedList`
## Sample Implementation: ArrayList (Figure 3.15 in textbook)
- Design principles:
	- `MyArrayList` will maintain the underlying array, the array capacity, and the current number of items stored in `MyArrayList`
	- `MyArrayList` will provide a mechanism to change the capacity of the underlying array by creating a larger array and move items from the old array to it.
	- `MyArrayList` will provide an implementation of `get` and `set` (List interface: `get`, `set`, `add`, `remove`, Iterator)
	- Will provide basic routines such as `size`, `isEmpty` (boolean), and `clear`, a version of `remove`, and two implementations of `add`. The `add` routines will increase the capacity if the size and capacity are the same.
	- Will provide a class that implements the iterator interface. This class will store the index of the next item in the iteration sequence and provide implementation of `next`, `hasNext`, and `remove`



#DSA #cs3345 #utd #CS #big-o #abstract-data-types 
