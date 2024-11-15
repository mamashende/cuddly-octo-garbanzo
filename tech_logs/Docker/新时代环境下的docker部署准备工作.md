### 安装
由于众所周知的审查问题，最后采取了二进制包手动安装的方式
https://docs.docker.com/engine/install/debian/#install-from-a-package


### docker镜像网络代理
由于众所周知的审查问题，除非能够访问到私有dockerhub镜像站，国内已经无法拉取任何镜像


#### dockerd代理 [¶](https://note.qidong.name/2020/05/docker-proxy/#dockerd%e4%bb%a3%e7%90%86)

在执行`docker pull`时，是由守护进程`dockerd`来执行。 因此，代理需要配在`dockerd`的环境中。 而这个环境，则是受`systemd`所管控，因此实际是`systemd`的配置。

```sh
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo touch /etc/systemd/system/docker.service.d/proxy.conf
```

在这个`proxy.conf`文件（可以是任意`*.conf`的形式）中，添加以下内容：

```sh
[Service]
Environment="HTTP_PROXY=http://127.0.0.1:port"
Environment="HTTPS_PROXY=http://127.0.0.1:port"
#port 当前本机使用的网络代理的服务端口
```


然后重启生效
```sh
sudo systemctl daemon-reload 
sudo systemctl restart docker
```



##### 好消息
[[2024-08-02]]
https://github.com/tech-shrimp/docker_installer
适用于国内的docker安装脚本

以及非root用户下使用docker
https://docs.docker.com/engine/security/rootless/
