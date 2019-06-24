# 构造数据类型
## 枚举类型
```C++
enum Day {SUN,MON,TUE,WED,THU,FRI,SAT}
```
默认第一个对应0，依次加1
指定时
```C++
enum Day {SUN=7,MON=1,TUE,WED,THU,FRI,SAT}
```
定义时
```C++
Day d1;
d1 = 1; //Error
SUN > MON; //true
```
算术运算
```C++
Day d;
cin >> d; //Error
d = d+1; //Error
d = (Day)(d+1); //OK
cout << d; //OK
```
通过输入赋值
(可以把一个枚举值赋值给一个整型变量，但不能把整型赋值给枚举型)
```C++
#include <iostream>
using namespace std;
int main(){
  Day d;
  int i;
  cin >> i;
  switch(i)
  {
    case 0: d = SUN; break;
    case 1: d = MON; break;
    case 2: d = TUE; break;
    case 3: d = WED; break;
    case 4: d = THU; break;
    case 5: d = FRI; break;
    case 6: d = SAT; break;
    default: cout << "Input Error!" << endl; exit(-1);
  }
  ......;
  switch(d)
  {
    case SUN: cout<< "SUN" << endl; break;
    case MON: cout<< "MON" << endl; break;
    case TUE: cout<< "TUE" << endl; break;
    case WED: cout<< "WED" << endl; break;
    case THU: cout<< "THU" << endl; break;
    case FRI: cout<< "FRI" << endl; break;
    case SAT: cout<< "SAT" << endl; break;
  }
  return 0;
}
```

## 向函数传递一维数组
```C++
#include <iostream>
using namespace std;

int max(int x[] , int num){
  int j=0;
  for(i=1 ; i<num ; i++){
    if(x[i] > x[j]){
      j = i;
    }
  }
  return j;
}

int main(){
  int a[10],index_max;
  index_max = max(a,10);
  cout<< a[index_max] <<endl;
  return 0;
}
```

## 一维字符数组
```C++
char s[10]; //表示长度为9的字符串
```
**初始化**
```C++
char s[10] = {'h','e','l','l','o','\0'};
char s[10] = {"hello"};
char s[10] = "hello";
char s[] = "hello";
```
## 二维数组
例子
```C++
#include <iostream>
using namespace std;
int main(){
  const int N=3;
  int a[N][N];
  int i,j;
  for(i=0 ; i<N ; i++){
    for(j=0 ; j<N ; j++){
      cin >> a[i][j];
    }
  }
  
  for(i=0 ; i<N ; i++){
    for(j=i+1 ; j<N ; j++){
      int temp = a[i][j];
      a[i][j] = a[j][i];
      a[j][i] = temp;
    }
  }
  
  for(i=0 ; i<N ; i++){
    for(j=0 ; j<N ; j++){
      cout << a[i][j] <<' ';
    }
    cout << endl;
    }
}
```
**初始化**

```C++
int a[2][3] = {{1,2,3},{4,5,6}};
int a[2][3] = {1,2,3,4,5};
int a[2][3] = {{1,2},{3,4}}
int a[][3] = {{1,2,3},{4,5,6},{7,8,9}}
```





