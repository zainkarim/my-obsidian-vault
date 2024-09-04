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

Iteratro here = list.iterator();

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



#DSA #cs3345 #utd #CS #big-o #abstract-data-types 