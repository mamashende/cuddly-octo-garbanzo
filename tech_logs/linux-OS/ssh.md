[OPENSSH 详解 - 入戏的小白 - 博客园 (cnblogs.com)](https://www.cnblogs.com/RXDXB/p/11672127.html)
[SSH 服务器 菜鸟教程 (cainiaojc.com)](https://www.cainiaojc.com/ssh/ssh-server.html)
服务端操作起来比较困难
客户端连接比较简单
故不用过于担心不会使用
[OpenSSH核心操作 | GitHub SSH连接_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Sx4y1y7B2/?spm_id_from=333.337.search-card.all.click&vd_source=fb42ad7665ae70e7e966d013226b0a96)

## 服务端
ubuntu上开启
[OpenSSH Server | Ubuntu](https://ubuntu.com/server/docs/service-openssh)
```bash
sudo apt install openssh-server -y
sudo systemctl start sshd.service

```

客户端使用ssh连接
```bash
ssh <需要连接的设备上的用户名>@<需要连接的设备的IP>
例：
ssh oyzy00@192.168.56.69
然后输入设备上设定的用户的密码，这里默认为123456
```
注：这里默认客户端已经安装，ssh客户端的安装因操作系统/IDE而异
windows下
```bat
winget install openssh
```

关于如何使ssh稳定连接不掉线的讨论
https://zhuanlan.zhihu.com/p/376629899?utm_id=0

test