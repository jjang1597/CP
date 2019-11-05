1. List
---
 - 설명
 -------------
  리스트란 구조체와 malloc() 사용하여 메모리할당 후 값을 넣고, 이렇게 생긴 변수들을 포인터를 활용하여 연결시켜주는 것입니다.
  -------------
 - 코드
 -------------
#include <stdio.h>
#include <stdlib.h>

typedef struct List {

	int d;
	
	struct List* p;
	
} LIST;

LIST* root = NULL;
LIST* last = NULL;

void addList(int a) {

	LIST* r = (LIST*)malloc(sizeof(LIST));
	
	r->d = a;
	
	r->p = NULL;

	if (root == NULL) {
	
		root = r;
		
	}
	
	else {
	
		last->p = r;
		
	}
	
	last = r;
	
}

int main() {

	addList(17);
	
	addList(24);
	
	addList(32);
	
	addList(15);

	while (root) {
	
		printf("%d\n", root->d);
		
		root = root->p;
		
	}
	
}
-------------
 - 종류
 -------------
  Single List
  Doubly List
  Circular List
-------------
2. Tree
---
 - 설명
 -------------
  트리란 구조체와 malloc()을 사용하여 메모리 할당 후, 포인터를 활용해 각각의 값들을 연결시켜주는 것입니다. 이렇게 연결된 형태가 나무와 닮았다하여 트리 라고 불립니다.
-------------
 - 코드
 -------------
#include <stdio.h>
#include <stdlib.h>

typedef struct Tree {

	int d;
	
	struct Tree* l, * r;
	
} T;

void print(T* p) {

	printf("%d\n", p->d);
	
	if (p->l) print(p->l);
	
	if (p->r) print(p->r);
	
}

T* mem() {

	T* p = (T*)malloc(sizeof(T));
	
	p->l = p->r = NULL;
	
	return p;
	
}

int main() {

	T* r, * r1, * r2, * l1, * l1r, * l1l;
	
	l1l = (T*)mem(); l1l->d = 7;
	
	l1r = (T*)mem(); l1r->d = 4;
	
	l1 = (T*)mem(); l1->d = 13; l1->l = l1l; l1->r = l1r;
	
	r2 = (T*)mem(); r2->d = 21;
	
	r1 = (T*)mem(); r1->d = 16; r1->r = r2;
	
	r = (T*)mem(); r->d = 24; r->l = l1; r->r = r1;
	
	print(r);
	
}
-------------
 - 구조
 -------------
                             24
                     13              16
                7          4                21
-------------
 - 종류
 -------------
  Binary Tree
  Binary Search Tree
  Complete Binary Tree
  Full Binary Tree
  -------------
  
  3. 그래프
  -------------
   - 설명
   -------------
    단순히 노드(N, node)와 그 노드를 연결하는 간선(E, edge)을 하나로 모아 놓은 자료 구조
    --------------
   - 종류
   --------------
    무방향 그래프, 방향 그래프, 가중치 그래프, 연결 그래프, 비연결 그래프, 사이클 그래프, 비순환 그래프, 완전 그래프
