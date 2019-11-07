
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

> ## List 설명사진
<div>
<img width="700" , src ="https://user-images.githubusercontent.com/50861700/68186521-b292bc80-ffe7-11e9-9ea7-72749e2759b7.png">	
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
> ## Tree 이해사진
<div>
<img width="700" , src ="https://user-images.githubusercontent.com/50861700/68188321-39e22f00-ffec-11e9-8620-89dc2d85a2b3.png">
</div>

> ## Tree 종류 
<div>
<img width="700", src = "https://user-images.githubusercontent.com/50861700/68191253-7add4200-fff2-11e9-888c-9a9f019d0884.png">
</div>


> ## graph 너비 우선 탐색

```c
#include <stdio.h>
int N, E;//N=총 노드 개수, E=총 간선 개수
int arr[101][101];
int queue[1001];
int visit[101];
int target;
int front = -1, rear = 0;
int cnt = 0;

void BFS() {
	if (front == rear) return; //1번조건
	else if (queue[front] == target) return; //2번조건
	else {
		cnt++;//탐색 횟수 ++
		int cur_front = queue[front];//현재 큐에 가장 앞에 있는 값
		for (int i = 0; i <= N; ++i) {
			if (visit[i]) continue;
			if (arr[cur_front][i] == 1) {
				visit[cur_front] = 1;
				queue[rear++] = i;
			}
		}
	}
	front++;//4번째 조건.
	BFS();
	return;
}

int main() {
	scanf_s("%d %d", &N, &E);
	for (int i = 0; i < E; ++i) {
		int a, b;
		scanf_s("%d %d", &a, &b);
		arr[a][b] = 1;
		arr[b][a] = 1;//인접행렬의 값을 채워줍니다. a에서 b까지 도달할 수 있고, 반대도 가능합니다.
	}
	printf("want to find : ");
	scanf_s("%d", &target);
	printf("start : ");//시작할 곳을 지정해줍니다.
	int start;
	scanf_s("%d", &start);
	front++;
	rear++;
	queue[front] = start;
	BFS();
	printf("total search : %d\n", cnt);
}
```

 > ## graph의 종류
<div>
	<img width ="700" , src ="https://user-images.githubusercontent.com/50861700/68191293-97797a00-fff2-11e9-80e9-fa2f31f08e35.png">
	</div>

> ## 소감 
```
화요일날 c프로그래밍 수업을 듣고 리스트를 처음 들었을 때 정말 무슨 소리인지 1도 몰랐습니다. 
그래서 심재창교수님이 친구들끼리 의논하라고 준시간에 나는 친구들과 의논하지 않고 혼자 이해해보려고 애썼습니다. 
하지만 저의 능력으로는 아직 이해하는 것이 부족했고 결국 옆친구의 도움을 받아서 이해하는 것에 성공을 하였습니다. 하지만 친구가 말로 설명할때는 이해할 수 있었지만 완전히 내것으로 만들려면 혼자 이해해보는것이 중요하다 생각하여 그 수업시간의 쉬는시간까지 없애면서 저는
트리,리스트를 이해하는 것에 힘을 썻습니다.
결국 쉬지는 못했지만 더 값진 것을 얻어 낸거 같아 기쁘고 
그래프 역시 카페에 올려주신 유튜버 "엔지니어대한민국"이라는 사람의 영상을 3번정도 반복해서 들었더니 어느정도 이해가 갔습니다.
그래프 설명을 듣고나니 수업시간에 배운 트리,리스트에 관한 영상도 보고싶어 찾아서 한두번정도 더보았습니다.
