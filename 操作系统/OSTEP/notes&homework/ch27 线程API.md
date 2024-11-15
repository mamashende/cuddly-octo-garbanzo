准确来说是POSIX线程API
详见
https://www.cs.cmu.edu/afs/cs/academic/class/15492-f07/www/pthreads.html
### 一点前言
当程序代码涉及到多线程时，就不再是顺序执行的了，因此需要改变之前阅读代码的顺序执行惯性思维，将不同的代码块视为同时执行的模块。


#### 线程创建
pthread_create()

#### 线程完成(同步)
pthread_join()
以下面的代码为例子，简单解释这两个API的参数列表

```C
#include<stdio.h>

#include<pthread.h>

#include<assert.h>

#include<stdlib.h>

  

typedef struct myarg_t

{

/* data */

int a;

int b;

}myarg_t;

  
  

typedef struct myret_t

{

/* data */

int x;

int y;

  

}myret_t;

  

void *mythread(void *arg){

  

myarg_t *m = (myarg_t *) arg;

printf("%d %d\n", m->a, m->b);

myret_t *r = malloc(sizeof(myret_t));

r->x = 1;

r->y = 2;

return (void *) r;

  

}

  
  

int main(int argc,char *argv[]){

pthread_t p;

int rc;

myret_t *m;

myarg_t args;

args.a = 114514;

args.b = 1919810;

//rc = pthread_create(&p,NULL,mythread,&args);

pthread_create(&p, NULL, mythread, &args);

pthread_join(p, (void **) &m);

printf("returned %d %d\n", m->x, m->y);

//pthread_join(p,)

//printf("done\n");

return 0;


```

pthread_create(&p, NULL, mythread, &args);

第一个参数p是一个pthread_t 类型，用于指定要等待的线程
第二个参数 attr 用于指定该线程可能具有的任何属性。一些例子包括设置栈大小，或关 于该线程调度优先级的信息。一个属性通过单独调用 pthread_attr_init()来初始化。有关详细信 息，请参阅手册。但是，在大多数情况下，默认值就行。在这个例子中，我们只需传入 NULL。

第三个参数指定线程运行的内容(可能是某个函数)

第四个参数负责传入运行的目标函数所需要的参数(多个参数则传入参数结构体)


pthread_join(p, (void **) &m);

第一个是 pthread_t 类型，用于指定要等待的线程。这个变量是由 线程创建函数初始化的（当你将一个指针作为参数传递给 pthread_create()时）。如果你保留 了它，就可以用它来等待该线程终止。

第二个参数是一个指针，指向你希望得到的返回值。因为函数可以返回任何东西，所 以它被定义为返回一个指向 void 的指针。**因为 pthread_join()函数改变了传入参数的值，所 以你需要传入一个指向该值的指针，而不只是该值本身。**
这里就是m的地址（但是要进行转换）
我们应该注意，必须非常小心如何从线程返回值。特别是，永远不要返回一个 指针，并让它指向线程调用栈上分配的东西。
实测如果mythread返回r的地址(return &t),那么在执行pthread_join时m将无法得到应该得到的地址，导致最后执行printf时访问非法内存Segmentation fault



### 锁相关API

#### 互斥锁
```C

int pthread_mutex_lock(pthread_mutex_t *mutex);
int pthread_mutex_unlock(pthread_mutex_t *mutex);
```


### 条件变量

```C
int pthread_cond_wait(pthread_cond_t *cond,pthread_mutex_t *mutex); 

int pthread_cond_signal(pthread_cond_t *cond);
```


### 编译运行方式

代码需要包括头文件 pthread.h 才能编译。
链接时需要 pthread库(pthread.h)，增加-pthread 标记。 例如，要编译一个简单的多线程程序，只需像下面这样做： 

```sh

gcc -o main main.c -Wall -pthread 
```

只要 main.c 包含 pthreads 头文件，你就已经成功地编译了一个并发程序。
