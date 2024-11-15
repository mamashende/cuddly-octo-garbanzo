https://www.cnblogs.com/kevingrace/p/5570197.html
上面的这篇文章有讲到

MySQL程序运行时，物理内存为MySQL分配了大量的物理地址空间，以提高执行的速率。**为了避免在执行消耗大量内存的操作时将MySQL所拥有的部分物理内存地址空间映射到swap分区上（比如出现了MySQL服务器Swap满了100%导致db很慢很卡的现象），可做一下调整（解决办法）：**  
1）改系统内核参数/proc/sys/vm/swappiness。调整系统使用swap分区的倾向性，数值越低越倾向于释放文件系统的cache，不能避免Linux系统使用swap分区。swappiness=0表示最大限度使用物理内存，然后才是swap分区。swappiness=100表示积极使用swap分区，并且将内存上的数据及时的映射到swap分区上。

/proc/sys/vm/swappiness的内容改成0（临时），/etc/sysctl.conf上添加vm.swappiness=0（永久）这个参数，Linux是倾向于使用swap，还是倾向于释放文件系统cache。在内存紧张的情况下，数值越低越倾向于释放文件系统cache。当然，这个参数只能减少使用swap的概率，并不能避免Linux使用swap。

2）改MySQL参数innodb_flush_method，开启O_DIRECT模式。Innodb的buffer pool会直接绕过文件系统cache来访问磁盘，但是redo log依旧会使用文件系统cache。Redo Log是覆写模式的，即使使用了文件系统的cache也不会占用太多

3）加MySQL配置参数memlock。将MySQL锁定在内存中防止被swapping out。这个参数会强迫mysqld进程的地址空间一直被锁定在物理内存上，对于os来说是非常霸道的一个要求。必须要用root帐号来启动MySQL才能生效。

4）指定MySQL使用大页内存（Large Page）。Linux上的大页内存是不会被换出物理内存的，和memlock有异曲同工之妙。

5）临时释放锁占据的swap。

这里尝试采用更改swappiness的值来解决

```sh
cat /proc/sys/vm/swappiness
```
得到默认的值为60


注意这个文件是运行时参数，仅能够临时修改，重启后还原
对于服务器而言，只要不停机，就不会变
将其改为0,表示最大限度利用内存，内存不够再用swap作为缓冲
```sh
sudo echo 0 > /proc/sys/vm/swappiness

```

要改回原来的值 重启系统即可

实测非root下无法修改这个数值

root下强行修改之后差点出了问题


简单粗暴的方法：直接取消使用swap分区
```sh
sudo swapoff /dev/xxx
```

https://www.cnblogs.com/liujiaxin2018/p/13869620.html