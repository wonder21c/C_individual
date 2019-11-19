> ## 1.출력
```c++
#include <iostream>
using namespace std;
int main() {
	cout << "Hello";
}
```

> ## 2.두 수 덧셈

```c++
#include <iostream>
using namespace std;
int main() {
	int a, b, c;
	cin >> a >> b;
	c = a + b;
	cout << c;

}
```
> ## 3. 덧셈 함수

```c++
#include<stdio.h>
struct Math {
	int a, b; //구조체의 멤버 변수
	int add() {
		return a + b;

	}

};

/*int Math::add() { //::는 스코프연산자
	return a + b;
} */

int main() {
	struct Math me = {2,3}; //Math 구조체 me는 객체
	
	printf("%d\n", me.add());
}
```

> ## 4.class

```c++
#include<stdio.h>
class Math {
private:
	int a, b; //구조체의 멤버 변수
public:
	Math(int x, int y) { //생성자
		a = x;
		b = y;
	}
	int add() {
		return a + b;

	}
};



int main() {
	Math me = {2,3}; //Math 구조체 me는 객체
	
	printf("%d\n", me.add());
}
```
