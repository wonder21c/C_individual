
||배열|리스트|
|-----|-----|-----|
|메모리 할당 효율||:o:|
|데이터 저장 값|:o:||
|중간 값추가/삭제||:o:|
 
> ## List
```c
#include <stdio.h>
#include <stdlib.h>
typedef struct list {
	int d;
	struct list* p;
} LIST;
LIST* root = NULL;
LIST* last = NULL;
void AddList(int a) {
	LIST* r = (LIST*)malloc(sizeof(LIST));
	r->d = a;
	r->p = NULL;
	if (root == NULL) root = r;
	else           last->p = r;
	last = r;
}
int main(void) {
	AddList(35);
	AddList(40);
	AddList(45);
	while (root) {
		printf("%d\n", root->d);
		root = root->p;
	}
}
```
<div>
<img width="500" , src ="">	
</div>



> ## Tree

```c
#include <stdio.h>
#include <stdlib.h>             
typedef struct Tree {
	struct Tree * l, * r;
	int d;
} T;
void print(T* p) {
	printf("%d\n", p->d); //free order
	if (p->l) print(p->l);
	if (p->r) print(p->r);
	
}
T* mem() {
	T* p = (T*)malloc(sizeof(T));
	p->l = p->r = NULL;
	return(p);
}
int main(void) {
	T* r, * r1, * r2, * l1;
	l1 = (T*)mem(); l1->d = 3;
	r2 = (T*)mem(); r2->d = 8;
	r1 = (T*)mem(); r1->d = 7; r1->r = r2;
	r = (T*)mem(); r->d = 5; r->l = l1;  r->r = r1;
	print(r);
}
```
