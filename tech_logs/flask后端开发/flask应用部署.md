测试是测试，部署还得自己来
[Flask + Gunicorn + Nginx 部署 - Ray Liang - 博客园 (cnblogs.com)](https://www.cnblogs.com/Ray-liang/p/4837850.html)
//这篇帖子有点老了，找找新东西看看

[Flask 应用如何部署 - #随风飘散 - 博客园 (cnblogs.com)](https://www.cnblogs.com/hellohorld/p/10033720.html)


[Gunicorn - WSGI server — Gunicorn 21.2.0 documentation](https://docs.gunicorn.org/en/stable/)
按照官方文档进行配置
[gunicorn 部署flask项目 - 三只松鼠 - 博客园 (cnblogs.com)](https://www.cnblogs.com/shenh/p/16824903.html)

由于目前只有一个客户端连接，因此可以不需要nginx进行反向代理啥的
但是目前好像还得试试nginx

目前的情况是文件传输在没有nginx的情况下部署成功了，测试时通过浏览器能够传输允许的文件格式

而且客户端那边实现起来也很简单


但是，这只是一小步！