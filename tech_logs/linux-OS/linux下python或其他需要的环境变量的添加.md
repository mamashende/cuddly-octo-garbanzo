对于linux下，则有不同的环境变量编辑方式（经过测试，通过apt安装的软件包会自动加入环境变量，但是macOS上可能存在问题，暂不讨论）//不一定，apt不一定会管理好环境变量问题，特别是使用了其他的shell之后（如zsh）可能会导致之前的环境变量失效
[[2024-03-26]]
linux下环境变量配置参考
https://www.cnblogs.com/youyoui/p/10680329.html
https://vic.kim/2021/04/25/Mac%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F%E9%85%8D%E7%BD%AE/


[在Linux中配置python环境变量 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/687097706)

大体上都是这样：
```sh
which python3
vim ~/.bashrc
export PATH=$PATH:/usr/bin/python3
source ~/.bashrc
```

关于为什么环境变量丢失的一点可能性：
之前apt安装的python自动将环境变量写入了~/.bashrc，但是后来自定义终端界面时，安装ohmyzsh时将~/.bashrc覆写了，原环境变量丢失了一部分

至于想pipenv这种作为python的一部分模块的应用要加入到环境变量的话，应该使用官方提供的文件路径添加至环境变量
[Pipenv 安装 — pipenv 2023.11.16.dev0 文档 --- Pipenv Installation — pipenv 2023.11.16.dev0 documentation (pypa.io)](https://pipenv.pypa.io/en/latest/installation.html#installing-pipenv)
