> ## 1.Quick Sorting

```c
#include <stdio.h>      /* printf */
#include <stdlib.h>     /* qsort */
int compare(const void* a, const void* b) //const는 상수화 시킨다.
{ return (*(int*)a - *(int*)b);} //타입캐스팅 (int*)는 int형으로 바꿔준다.
int main() { int v[] = {3,1,2,5,4}; 
int n; qsort(v, 5, sizeof(int), compare); //소수는 double
for (n = 0; n < 5; n++) 
	printf("%d ", v[n]); 
	  return 0;}
```
