### C语言初始化数组元素的几种方法
```c++
//Unless that value is 0 (in which case you can omit some part of the initializer and 
//the corresponding elements will be initialized to 0), there's no easy way.

//Don't overlook the obvious solution, though:
int myArray[10] = { 5, 5, 5, 5, 5, 5, 5, 5, 5, 5 };

//Elements with missing values will be initialized to 0:
// initialize to 1,2,0,0,0...
int myArray[10] = { 1, 2 }; 

//So this will initialize all elements to 0:
int myArray[10] = { 0 }; // all elements 0

//In C++, an empty initialization list will also initialize every element to 0. This is not allowed with C:
int myArray[10] = {}; // all elements 0 in C++

//Remember that objects with static storage duration will initialize to 0 if no initializer is specified:
static int myArray[10]; // all elements 0
//And that "0" doesn't necessarily mean "all-bits-zero", 
//so using the above is better and more portable than memset().
//(Floating point values will be initialized to +0, pointers to null value, etc.)
```

### C++动态数组
```cpp
//申请动态数组
int size = 50;
int *p=new int[size]; 

//释放动态数组
delete p;
```

### 使用数组初始化vector的方法
```cpp
//With only language support you can use:

int tmp[] = { 10, 20, 30 };
std::vector<int> v( tmp, tmp + 3 ); // use some utility to avoid hardcoding the size here
```
