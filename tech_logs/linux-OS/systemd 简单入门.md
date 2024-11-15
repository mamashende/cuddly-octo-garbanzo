https://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html
为了更好的了解mysql和redis的开机自动启动的部署原理，有必要学习systemd
https://wiki.archlinuxcn.org/wiki/Systemd
https://cloud.tencent.com/developer/article/1516125

下面是redis的systemd配置样例
```service
[Unit]
Description=Redis data structure server
Documentation=https://redis.io/documentation
Wants=network-online.target
After=network-online.target

[Service]
ExecStart=/usr/local/redis-server/bin/redis-server /usr/local/redis-server/redis.conf --supervised systemd --daemonize no
LimitNOFILE=10032
NoNewPrivileges=yes
Type=notify
TimeoutStartSec=0
TimeoutStopSec=0
UMask=0077
User=redis
Group=redis

[Install]
WantedBy=multi-user.target
```

