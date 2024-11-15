# gcc:
- --verbose返回编译日志
```bash
gcc xxxx.c --verbose
```
- -o 编译得到文件名xxxx的可执行文件，linux下可执行文件无后缀

```bash
gcc xxxx.c -o xxxx
```
- -WL 显示链接相关内容

- -E 输出预编译文件
- -c 输出.o

## ld 命令

```bash
ld xxx.o 
```
- -e main



# gdb
- starti 从程序的第一条命令开始执行
- layout asm 一个简单的查看汇编的GUI

