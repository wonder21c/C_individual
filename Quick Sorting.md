> ## 1.Quick Sorting(간단)

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

> ## 2.Quick Sorting(풀어쓴것)
```c
#include<stdio.h>
#define LEN 8

void qs(int v[], int left, int right) {
	int pivot, pi, l, r, dir;
	if (left < right) {
		dir = 0;
		l = left; r = right; pi = left;
		pivot = v[pi];
		while (l < r) {
			if (dir == 0) {
				if (pivot < v[r]) r--;
				else {
					v[pi] = v[r];
					pi = r;
					if (l != r) l++;
					dir = 1;
				}
			}
			if (dir == 1) {
				if (pivot > v[l]) l++;
				else {
					v[pi] = v[l];
					pi = l;
					if (l != r) r--;
					dir = 0;
				}
			}
		}
		v[r] = pivot;
		qs(v, left, r - 1);
		qs(v, r + 1, right);
	}
	return;
}
void main() {
	int i;
	int v[LEN] = { 8,17,6,5,-44,3,2,1 };
	for (i = 0; i < LEN; i++) printf(" %d", v[i]); printf("\n");
	qs(v, 0, LEN - 1);
	for (i = 0; i < LEN; i++) printf(" %d", v[i]); printf("\n");
}
```
