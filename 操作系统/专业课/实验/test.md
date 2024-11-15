以下是根据您提供的模板和实验1的内容生成的实验报告的Markdown格式：

```markdown
## 一、实验概述
### 1.实验名称
实验1

### 2.实验目的
- 学习Linux 0.11应用程序项目的生成和运行。
- 掌握在Linux 0.11环境中使用vi编写和调试C程序。

### 3.实验类型（演示性、验证性、设计研究性）
设计研究性

### 4. 实验内容
- 在Linux 0.11系统中添加源代码并调试。
- 生成和运行Linux 0.11应用程序项目。

## 二、实验环境
- 操作系统：Linux 0.11
- 编译器：gcc
- 语言：C语言

## 三、实验过程
### 设计思路和流程图
- 任务1：模仿源代码添加新的打印语句。
- 任务2：生成和运行Linux 0.11应用程序项目。

### 算法实现
- 任务1：添加源代码以打印字符串“Hello Linux！”。
- 任务2：编写两个C程序并通过Makefile进行编译链接。

### 需要解决的问题及解答
- 问题：如何在Linux 0.11中添加和调试代码。
- 解答：通过在指定位置添加代码并使用调试功能观察输出。

### 主要数据结构、实现代码及其说明
```c
// add.c
int add(int a,int b) {
	return a+b;
}
```

```c
// main.c
#include<stdio.h>

int main(){
	int a=10;
	int b=200;
	int c =	add(a,b);
	printf("a = %d , b = %d\n ",a,b); 
	printf("a + b = %d\n ",c); 
	return 0;
}
```

### 源程序并附上注释
```makefile
#Makefile for compiling add.c and main.c

# Compiler
CC = gcc

# Compiler flags
CFLAGS = -Wall

# Source files
SRCS = add.c main.c

# Object files
OBJS = $(SRCS:.c=.o)

#Executable
TARGET = app

#DEFAULT target
all: $(TARGET)

#Compile source files to object files
%.o:%.c
	$(CC) $(CFLAGS) -c $< -o $@

$(TARGET):$(OBJS)
	$(CC) $(OBJS) -o $(TARGET)

#Clean
clean:
	rm -f $(OBJS) $(TARGET) 
```

### 程序运行时的初值和运行结果
- 运行结果：成功编译链接并运行程序，输出结果为`a = 10 , b = 200`和`a + b = 210`。

## 四、实验体会
- 在实验中，我们成功地在Linux 0.11系统中添加了新的源代码，并通过对代码进行调试，观察到了预期的输出结果。
- 通过编写和运行C程序，我们加深了对Linux 0.11应用程序项目生成和运行的理解。
- 实验过程中，我们遇到了一些编译和链接的问题，但通过查阅资料和不断尝试，最终解决了这些问题。
- 通过本次实验，我们学习到了如何在Linux环境下进行C语言编程和调试，这对于我们未来在Linux系统下进行软件开发具有重要意义。

![[Pasted image 20241105195410.png]]
![[Pasted image 20241105200741.png]]
![[Pasted image 20241105201120.png]]
![[Pasted image 20241105210510.png]]
```

请注意，图片引用已经保留，并且没有进行修改。您可以将上述内容复制到Markdown编辑器中查看格式效果。
