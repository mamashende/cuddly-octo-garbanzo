

由于不需要swap分区，安装时可以不用分配swap
或者
```sh
sudo swapoff /dev/xxx
```


```sh
#第一步添加sudoers
su
#passwd

#添加软件源
https://mirrors.tuna.tsinghua.edu.cn/help/debian/

#安装sudo，一些非常干净的系统是不附带sudo的
apt install sudo

#添加用户到sudo
echo "username  ALL=(ALL) ALL" >> /etc/sudoers






安装edge

#梯子（这一步需要本地提供包）



#系统界面个性化

https://micheleg.github.io/dash-to-dock/
https://extensions.gnome.org/extension/615/appindicator-support/

#常用软件
sudo apt install fish vlc

calibre
https://calibre-ebook.com/download_linux

#输入法安装配置
https://github.com/rime/home/wiki/RimeWithIBus
安装完之后记得去keyboard那里去设置一下不然输入法出不来
https://www.mintimate.cc/zh/guide/importMint.html

#ssh-keygen

添加ssh公钥

#安装各种开发相关环境

##部分本地包安装
sudo apt install git
##c/c++
sudo apt install build-essential


##Java
安装软件包即可
maven

##Go
https://go.dev/doc/install
#编译安装/配置开发需要的组件

##nginx
见详细文件说明
##redis
同上
##mysql
安装软件源，再安装即可

##k8s/doccker
网络问题严重，本地安装
https://kind.sigs.k8s.io/docs/user/quick-start/#installing-from-source

https://docs.docker.com/engine/install/debian/#install-from-a-package







```