软件安装就不多说了
```sh
sudo apt instal ./xxxxx.deb
# ./xxxxx.deb 即为想要的安装包
```

清理snap残留物
```sh
sudo snap list
# 列出所有的snap安装的软件
```


列出所有用apt安装的包：
```sh
sudo dpkg --list | grep xxxx
# grep 便于关键词查找
```
清理apt残留物
```sh
sudo apt-get --purge remove xxxxx
```


关于deb包的一些基本知识：
https://www.cnblogs.com/zoghin/p/15205055.html

阻止更新一些重要软件包

如果你有一系列软件包需要在使用APT进行更新时排除，你可以使用APT的"hold"功能来实现。以下是一系列软件包排除更新的步骤：

1. 打开终端，并使用root或具有管理员权限的用户登录。

2. 创建一个文本文件，列出需要排除更新的软件包。每个软件包占一行，例如：
   ```
   mysql-server
   apache2
   openjdk-11-jdk
   ```

3. 将文本文件保存为一个适当的名称，例如exclude-packages.txt。

4. 使用以下命令读取文本文件中的软件包列表，并将它们标记为"hold"：
   ```
   xargs -a exclude-packages.txt sudo apt-mark hold
   ```

   这将针对每个软件包执行`apt-mark hold`命令，将它们标记为"hold"状态，以阻止它们被更新。

现在，当你使用APT进行软件包更新时，列出的软件包将被排除在更新列表之外。

如果你想解除某个软件包的"hold"状态，使其可以再次被更新，可以使用以下命令：
```
sudo apt-mark unhold <package-name>
```
其中，`<package-name>`是要解除"hold"状态的软件包的名称。

请注意，当你决定解除"hold"状态并更新软件包时，确保在更新之前备份任何重要数据，并确保能够处理潜在的兼容性或配置变更问题。


### 清理失效软件源的方法
方法比较多，
一部分软件源放在 /etc/apt/sourcelist.d/ 下，直接清理即可
某些带有gpg公钥的删除即可

然后 apt update