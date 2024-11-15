或许redis有某种保护机制，导致其一旦启动就无法通过systemctl强行退出
正常的退出方式或许需要通过登陆redis之后才能进行

目前的解决方案是在开发环境下不注册为systemd服务，采用手动启动停止的方式进行管理
在生产环境下才进行注册部署

启动指令：
```sh
cd  ~/install_cache
sudo /usr/local/redis-server/bin/redis-server
```
切换到特定目录再启动，防止.rdb文件到处乱放，重启只需退出即可