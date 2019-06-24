# Node
## 指针
**指针赋值**
```C++
int x,*p,*p1;
double y,*q;
p = &x; //OK
q = &y; //OK
p = &y; //Error
p1 = p; //PK
p = 0; //OK,p不指向任何变量
p = 120; //Error, 120为int型
p = (*int)120; //OK
```
**指针类型常量**
```C++
int x,y;
int *const p = &x; //p必须初始化
*p = 1; //OK
p = &y;
```
```C++
int x,y;
const int *const p = &x;
*p = 1; //Error
p = &y; //Error
```

## 动态变量
```C++
int *p;
p = new int[n]; //p指向新创建的int型动态变量
delete []p;
```
```C++
int x,*p;
p = &x;
delete p; //Error
```

## 链表
```C++
struct Node{
  int content;
  Node *next;
}
Node *head = NULL;
Node *p = new Node;
p -> content = a;
p -> next = NULL;
head -> next = p;
```
插入在i
```C++
Node *q = head;
int j=1;
while(j<i){
  if(q->next == NULL){
    break;
  }
  q = q->next;
  j++;
}
if(j == i){
  p->next = q->next;
  q->next = p;
}
```

## 引用类型
```C++
int x;
int &y = x; //必须初始化
```

