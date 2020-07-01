

# C++ Primer 笔记



## 第一部分 c++基础

### 二章 

- 引用

  ```
  指左值引用: 必须被初始化绑定
   c++11添加了右值引用(p471)
   不存在引用的数组 比如int &r[10] = ...; //错误
  ```

- const

  ```c++
  编译时会将变量名直接替换为值
  
  对常量的引用
  const int c1 = 10;
  const int & r1 = c1; //对常量的引用,简称“常量引用”
  int & r2 = c1; 不允许: //非常量引用不能绑定到常量上(c1)
  
  指向常量的指针
  const double pi = 3.14;
  const double* p1 = &pi;
  
  const指针(指针的值不能变(地址))
  double* const p2 = &pi; //p2不能赋值
  
  顶层const(pointer本身是const); //有指针*时,const在右边,当然const int c1这种也是顶层const
  底层const(pointer指向的对象是const); //const在左边
  ```

- auto

  ```c++
  auto会忽略顶层const而保留底层const
  字面值: const auto &j = 42; 不能auto &j = 42; 
  但const int c = 10; 可以auto &g = c;
  ```
  
- decltypre
  
  ```c++
  const int c = 0,&r = c;
  decltype(c) a = 42; //a是const int
  decltype(r) b = a; //b是const int &
  ```
  
  
  
### 三章 string & vector

- getline(流对象,string)

  ```
  把流对象的
  ```

- 数组

  ```c++
  指针也是迭代器: p++
  begin()和end()
  int a[] = {0,1,2,3,4,5};
  int *p_begin = begin(a);
  int *p_end = end(a);
  ```
  
  
  
### 四章

- 强制类型转换

  ```c++
  static_cast, dynamic_cast, const_cast, reinterpret_cast;
  static_cast: 不包含底层const
    比如double b = static<double>(a)/c;
  const_cast: 改变底层const
    const char* pc;
    char* p = const_cast<char*>(pc);
  dynamic_cast<type*>或dynamic_cast<type&>或dynamic_cast<type&&>:type必须为类类型
  ```

### 六章

- 函数调用

  ```c++
  完成2步:
  	1. 用实参初始化形参
    2. 主调函数执行被中断, 控制权交到被调函数
  ```

  


