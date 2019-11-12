> ## 1.스택
```c
#include<stdio.h>
int sp = -1; //스택포인터
int v[1000]; //스택
void push(int a) {
	++sp;
	v[sp] = a;
}
int pop() {
	return(v[sp--]);
}
int main() {
	push(5); 
	push(3);
	printf("%d\n", pop()); 
	printf("%d\n", pop());
}
```
