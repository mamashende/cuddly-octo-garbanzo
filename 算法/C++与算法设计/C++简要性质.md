由于在算法表达上，C++仍然占据主导地位，因此有必要学习一些C++性质

函数传参
传值（传拷贝）
传指针
传引用（传指针跟传引用区别不大，不过建议传引用，这样更安全，如果是写C，那另当别论）


构造/析构
new/delete

深拷贝/浅拷贝
- 深拷贝将对象完全复制一份
- 浅拷贝只创建一个对于对象的引用


移动语义
为了减少复杂对象赋值时的深拷贝操作造成的性能损失
此时移动语义 move操作更好



函数指针
用得比较少，一函数为参数，实际上是传入函数所在代码的地址



函数对象/lambda表达式
匿名函数


虚函数
纯虚函数（接口interface）



初始化列表
在 C++ 中，`return {it->second, i};` 这种类型的返回值是使用初始化列表或者称为列表初始化（list initialization）实现的。这种语法形式可以用来返回一个包含多个值的数据结构，如 `std::pair` 或者自定义的结构体。

在这种情况下，`{it->second, i}` 表示一个初始化列表，它将会被用来构造一个合适的对象。编译器会根据返回类型来推断应该如何构造这个对象。


### 容器
STL容器基于模板实现
支持多层容器嵌套实现复杂数据结构


迭代器
迭代器是指针的抽象封装，通过对迭代器做运算，实现了对于容器内存空间的灵活访问，而指针只支持连续内存空间访问

迭代器支持大部分指针运算
```cpp
//迭代器使用例子

struct message

{

/* data */

bool flag;

int a;

string messages;

};

  
  

int main(){

int n = 10;

message m = {1,114514,"haha"};

vector<message> test(n , m);

  

vector<message> :: iterator it = test.begin();

  
//使用迭代器实现复杂对象构成的数组的遍历
for (;it != test.end();it++)

{

(*it).flag = 0;

}

  

  

}
```

为了使迭代器通用性更好，标准库中还有一些相关函数



 容器的常见构造函数
 ```cpp
ContainerType c(num);//构造容器c，容器内部是Type类型的数组，数组大小是num

//例子如下
int n = 10;
vector<int> test(n);

struct message

{

/* data */

bool flag;

int a;

string messages;

};

  
  

int main(){

int n = 10;

vector<message> test(n);

  

}



ContainerType c(num , x);//并将容器数组内容赋值为x(x为数组元素的类型)
int n = 10;

message m = {1,114514,"haha"};

vector<message> test(n , m);

ContainerType c(beg,end);//beg,end是迭代器，所以这个可以视为slice操作
```

容器常见方法：
```cpp
int s = c.size();
bool b = c.empty();
c.resize(num);//重新设置容器大小
c.resize(num , x);
c.clear();
```

容易弄混淆的一点，一个容器是一个对象
例如
```cpp
int n = 10;

vector<message> test(n);
```
test对象是一个体，内部包含一个由message结构体构成的数组



关于栈
1. 一个栈（无穷大）的进栈序列为 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1,2,3, \cdots ,n") 有多少个不同的出栈序列？

https://oi-wiki.org/math/combinatorics/catalan/


队列

https://oi-wiki.org/ds/queue/

双栈模拟队列：
栈a负责入栈元素(入队)
栈b负责出栈元素(出队)


入队：压入栈a即可

出队：
当栈b为空时，将a中元素压入b，然后依次弹出即可
当栈b不为空栈，先弹出元素直至空栈，然后回到栈为空时的操作


vector
不定长数组

list
linked list 链表

单向迭代器 

内存池 


优先队列
可以实现根据优先级排序的队列
 本质是一个大根堆


