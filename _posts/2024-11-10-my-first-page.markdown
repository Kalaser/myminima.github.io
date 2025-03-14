---

layout: post
title:  "C/C++基础知识"
date:   2024-11-10 19:36:59 +0800
categories: jekyll update

---

### C 语言知识点

#### 1. **基本语法**

- **数据类型**：`int`, `char`, `float`, `double`, `long`, `short` 等基本类型。
- **变量声明和初始化**：

````c
int a = 10;
char ch = 'A';
````

- **控制结构**：`if`, `else`, `for`, `while`, `switch`, `break`, `continue` 

- **函数定义和调用**：

````c
int add(int a, int b) 
{
return a + b;
int result = add(3, 4);
}
````

#### 2.**指针**

- **定义和使用**：指针是 C 语言的核心，允许直接访问内存。

- **指针算术**：指针可以进行加减运算，指向数组元素、结构体成员等。

  ````C
  ptr++;  // 指向下一个内存位置
  ````
  
- **动态内存分配：**

  使用malloc 、calloc 、realloc 、free 函数
  ````C
  int *arr = (int *)malloc(sizeof(int) * 10);
  free(arr);
  ````
#### 3.**结构体与联合体**

- **结构体:**用来组合不同类型的数据。

  ````C
  struct Person {
      char name[50];
      int age;
  };
  
  struct Person p1 = {"Alice", 30};
  ````
  
- **联合体:**不同的数据共用同一块内存，节省内存。

  ````c
  union Data {
        int i;
        float f;
    };
  ````
  


#### 4. **文件操作**

- **文件读取和写入:**

````c
  FILE *fp = fopen("file.txt", "r");
  char str[100];
  fgets(str, 100, fp);
  fclose(fp);
````



#### 5. **内存管理**

- **堆和栈**：栈用于局部变量，堆用于动态分配的内存。
- **指针和内存泄漏**：指针的误用可能导致内存泄漏，使用 `free()` 释放动态分配的内存。

````c
#include <stdio.h>
#include <stdlib.h> // 用于 malloc 和 free

void stackExample() {
    int stackVariable = 10; // 栈上的局部变量
    printf("Stack variable value: %d, address: %p\n", stackVariable, (void*)&stackVariable);
}

void heapExample() {
    int* heapVariable = (int*)malloc(sizeof(int)); // 在堆上分配内存
    if (heapVariable == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }

    *heapVariable = 20; // 给堆上的变量赋值
    printf("Heap variable value: %d, address: %p\n", *heapVariable, (void*)heapVariable);

    free(heapVariable); // 释放堆内存
    heapVariable = NULL; // 防止悬空指针
}

void memoryLeakExample() {
    int* leakedMemory = (int*)malloc(sizeof(int)); // 分配内存
    if (leakedMemory == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }

    *leakedMemory = 30; // 使用动态分配的内存
    printf("Leaked memory value: %d, address: %p\n", *leakedMemory, (void*)leakedMemory);

    // 演示内存泄漏：未释放内存
    // free(leakedMemory); // 应该释放内存，但此行被注释掉
    // leakedMemory = NULL;
}

int main() {
    printf("Demonstrating stack and heap usage:\n");
    stackExample(); // 栈示例
    heapExample();  // 堆示例

    printf("\nDemonstrating memory leak:\n");
    memoryLeakExample(); // 演
````

---



###  C++ 语言知识点

#### 1. **面向对象编程（OOP）**		

  - **类与对象**：

  - **构造函数与析构函数**：构造函数用于初始化对象，析构函数用于清理。

    ````c++
    class MyClass {
    public:
        MyClass() { cout << "Constructor\n"; }
        ~MyClass() { cout << "Destructor\n"; }
    };
    ````
    
  - **继承**：
    
    - 基类和派生类
    - 继承方式：`public`, `protected`, `private`
    ````c++
    class Animal {
    public:
        void sound() { cout << "Animal sound"; }
    };
    class Dog : public Animal {
    public:
        void sound() { cout << "Woof!"; }
    };
    ````
    
  - **多态性**：通过虚函数实现动态绑定。

    ````c++
    class Shape {
    public:
        virtual void draw() { cout << "Drawing Shape"; }
    };
    class Circle : public Shape {
    public:
        void draw() override { cout << "Drawing Circle"; }
    };
    ````

#### 2. **模板（Templates）**

  - **函数模板**：用来创建通用函数。

    ````c++
    template <typename T>
    T add(T a, T b) {
        return a + b;
    }
    ````

  - **类模板**：用来创建通用类。

    ````c++
    template <class T>
    class Box {
    private:
        T value;
    public:
        void setValue(T v) { value = v; }
        T getValue() { return value; }
    };
    ````

#### 3. **标准模板库（STL）**

  - **容器**：如 `vector`, `list`, `deque`, `map`, `set` 等。
  - **算法**：如 `sort`, `find`, `accumulate` 等。
  - **迭代器**：通过迭代器访问容器元素。

````c++
#include <vector>
#include <iostream>
using namespace std;
int main() {
    vector<int> v = {1, 2, 3, 4, 5};
    for(auto it = v.begin(); it != v.end(); ++it) {
        cout << *it << " ";
    }
    return 0;
}
````



#### 4.**智能指针**

  - `unique_ptr`、`shared_ptr` 和 `weak_ptr`：

    C++11 引入的智能指针，用于自动管理内存。

    ````c++
    #include <memory>
    unique_ptr<int> ptr(new int(10));
    ````

#### 5.**异常处理**

  - `try`, `catch`, `throw`：

````c++
//C++ 提供了异常处理机制，能够捕获并处理程序中的错误。
cppCopy codetry {
    throw 10;
} catch (int e) {
    cout << "Caught exception: " << e;
}
````


---

### C和C++ 公共知识点

#### 1.**内存模型**

  - **栈内存**和**堆内存**：栈用于存储局部变量，堆用于动态分配内存。
  - **内存泄漏**：动态分配的内存如果没有被正确释放，会导致内存泄漏。

#### 2.**预处理器指令**

  - **宏定义**：使用 `#define` 定义宏，类似于常量或函数的替代。

    ````c
    #define PI 3.14
    ````

  - **条件编译**：根据不同的条件编译代码块。

    ````c
    #ifdef DEBUG
    printf("Debug mode\n");
    #endif
    ````

#### 3.**C 和 C++ 的差异**

  - **C++ 支持面向对象编程**，而 C 仅支持过程化编程。
  - **C++ 支持函数重载**和**运算符重载**。
  - **C++ 引入了标准模板库（STL）**，这使得 C++ 在容器和算法方面有了更强大的支持。

  
