## `do...while` loop
```c
do
	//statement
while(condition)
```
```c
#include <stdio.h>

int main(void) {
	unsigned int counter = 1;

	do {
		printf("%u ", counter);
	} while (++counter <= 10);
}
```
Output: `1 2 3 4 5 6 7 8 9 10`
## For Loop
```c
for(x = 1; x <= 10; ++x) {
	if (x==5) {
		break;
	}
}
```

#linux #unix #cs3377 #CS #utd #C