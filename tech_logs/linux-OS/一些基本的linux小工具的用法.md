[Linux命令搜索引擎 命令，Linux Linux命令搜索引擎 命令详解：最专业的Linux命令大全，内容包含Linux命令手册、详解、学习，值得收藏的Linux命令速查手册。 - Linux 命令搜索引擎 (gitee.io)](https://jaywcjlove.gitee.io/linux-command/)


## tar
[tar 命令，Linux tar 命令详解：将许多文件一起保存至一个单独的磁带或磁盘归档，并能从归档中单独还原所需文件。 - Linux 命令搜索引擎 (wangchujiang.com)](https://wangchujiang.com/linux-command/c/tar.html)
#### zip格式

压缩： zip -r [目标文件名].zip [原文件/目录名]  
解压： unzip [原文件名].zip  
注：-r参数代表递归

#### [](https://wangchujiang.com/linux-command/c/tar.html#tar%E6%A0%BC%E5%BC%8F%E8%AF%A5%E6%A0%BC%E5%BC%8F%E4%BB%85%E4%BB%85%E6%89%93%E5%8C%85%E4%B8%8D%E5%8E%8B%E7%BC%A9)tar格式（该格式仅仅打包，不压缩）

打包：tar -cvf [目标文件名].tar [原文件名/目录名]  
解包：tar -xvf [原文件名].tar  
注：c参数代表create（创建），x参数代表extract（解包），v参数代表verbose（详细信息），f参数代表filename（文件名），所以f后必须接文件名。

#### [](https://wangchujiang.com/linux-command/c/tar.html#targz%E6%A0%BC%E5%BC%8F)tar.gz格式

方式一：利用前面已经打包好的tar文件，直接用压缩命令。

压缩：gzip [原文件名].tar  
解压：gunzip [原文件名].tar.gz

方式二：一次性打包并压缩、解压并解包

打包并压缩： tar -zcvf [目标文件名].tar.gz [原文件名/目录名]  
解压并解包： tar -zxvf [原文件名].tar.gz  
注：z代表用gzip算法来压缩/解压。

#### [](https://wangchujiang.com/linux-command/c/tar.html#tarbz2%E6%A0%BC%E5%BC%8F)tar.bz2格式

方式一：利用已经打包好的tar文件，直接执行压缩命令：

压缩：bzip2 [原文件名].tar  
解压：bunzip2 [原文件名].tar.bz2  
方式二：一次性打包并压缩、解压并解包

打包并压缩： tar -jcvf [目标文件名].tar.bz2 [原文件名/目录名]  
解压并解包： tar -jxvf [原文件名].tar.bz2  
注：小写j代表用bzip2算法来压缩/解压。

#### [](https://wangchujiang.com/linux-command/c/tar.html#tarxz%E6%A0%BC%E5%BC%8F)tar.xz格式

方式一：利用已经打包好的tar文件，直接用压缩命令：

压缩：xz [原文件名].tar  
解压：unxz [原文件名].tar.xz  
方式二：一次性打包并压缩、解压并解包

打包并压缩： tar -Jcvf [目标文件名].tar.xz [原文件名/目录名]  
解压并解包： tar -Jxvf [原文件名].tar.xz  
注：大写J代表用xz算法来压缩/解压。

#### [](https://wangchujiang.com/linux-command/c/tar.html#tarz%E6%A0%BC%E5%BC%8F%E5%B7%B2%E8%BF%87%E6%97%B6)tar.Z格式（已过时）

方式一：利用已经打包好的tar文件，直接用压缩命令：

压缩：compress [原文件名].tar  
解压：uncompress [原文件名].tar.Z  
方式二：一次性打包并压缩、解压并解包

打包并压缩： tar -Zcvf [目标文件名].tar.Z [原文件名/目录名]  
解压并解包： tar -Zxvf [原文件名].tar.Z  
注：大写Z代表用ncompress算法来压缩/解压。另，ncompress是早期Unix系统的压缩格式，但由于ncompress的压缩率太低，现已过时。