# C Programming Class

*디버그 -> 속성 -> C/C++ -> 전처리기 -> 전처리기 정의에 ;_CRT_SECURE_NO_WARNING를 추가 시킨다.*

1. 명령창에서 계산기를 구현하시오. 매개변수가 모자라면 프로그램을 종료하시오.

#include <stdio.h>

#include <stdlib.h>

int main(int n, char* v[]) {

	int a, b, c;

  if (n < 4) {
  
    printf("매개변수가 모자랍니다.\n");
    
    exit(0);
    
  }

	a = atoi(v[1]);
	
	b = atoi(v[3]);

	switch(v[2][0]) {
	
	case '+': c = a + b; break;
	
	case '-': c = a - b; break;
	
	case '*': c = a * b; break;
	
	case '/': c = a / b; break;
	
	case '%': c = a % b; break;
	
	default: c = 0; break;
	
	}

	printf("%d\n", c);
	
}

2. my.txt 에 첫줄에 33 다음 줄에 22들어 있다. 이를 읽고 add() 함수를 이용하여 더하고 결과를 출력하시오. 반드시 오류에 대해 처리를 포함하시오.

#include <stdio.h>

#include <stdlib.h>

int add(int a, int b);

int main() {

	int a, b;

	FILE* fp = fopen("my.txt", "r");
	
	if (fp == NULL) { printf("파일이 없습니다.\n"); exit(0); }
	
	fscanf(fp, "%d %d", &a, &b);
	
	fclose(fp);

	printf("%d\n", add(a, b));
	
}

int add(int a, int b) {

	return a + b;
	
}

my.txt
33
22

3. 예상되는 문제를 하나 만들고, 코딩을 하시오.

재귀함수를 이용하여 1부터 입력받은 수까지의 합을 화면에 출력하시오.

#include <stdio.h>

int a(int i) {

	if (i == 0) {
	
		return 0;
		
	}
	
	return i + a(i-1);
	
}

int main() {

	int t;
	
	scanf("%d", &t);
	
	printf("%d\n", a(t));
	
}

4. 두명의 구조체 정보를 배열에 초기화하고 포인터로 화면에 출력하시오.

#include <stdio.h>

struct User {

	int a;
	
	char name[30];
	
} u[2] = {{20, "jch"}, {18, "hbc"}};

int main() {

	struct User* p;
	
	p = u;
	
	printf("%d %s\n", p->a, p->name);
	
	p++;
	
	printf("%d %s\n", p->a, p->name);
	
}
