[[2024-04-02]]
https://www.liaoxuefeng.com/wiki/1016959663602400/1017801751919456
利用python直接操作SQLite数据库

https://juejin.cn/s/sqlite%E6%94%AF%E6%8C%81%E8%BF%9C%E7%A8%8B%E5%90%97
关于利用网络实现数据库同步的工具


https://pythondjango.cn/django/rest-framework/1-RESTfull-API-why-DRF/

这下不得不用python开发后端力（）
因为其他语言也不会QAQ,而且模型那边也是python,这样对接起来快一点，虽然有被嘲笑是低技术的风险，但是能跑起来就行，技术是第二位的，毕竟也只是低负载。
https://blog.ailemon.net/2020/11/09/dl-best-deployment-python-impl-http-api-server/


关于模型部署的一点参考
https://github.com/aipredict/ai-deployment/blob/master/deploy-pytorch-in-daas/README.md
评价为太贵，用不起，结束


https://www.cnblogs.com/danny92/p/14978973.html
评价为过时了

https://juejin.cn/post/7273432426755506231
基本上轻量级的模型部署都在用flask,django用的少


[基于 docker 和 Flask 的深度学习模型部署！ - 掘金 (juejin.cn)](https://juejin.cn/post/7082974553034948621)
评价为写的不太行

[使用 Flask API 部署深度学习模型 |由 Dharmaraj |中等 --- Deploying Deep Learning Model using Flask API | by Dharmaraj | Medium](https://medium.com/@draj0718/deploying-deep-learning-model-using-flask-api-810047f090ac)
#### 一些小的技术细节
使用flask/django
采用C/S模式
需要用docker的原因是因为需要同时部署三个不同的模型，三个模型的环境依赖各不相同，目前计划是放入docker中保证稳定运行


简要的过程与描述：

设计一个服务端，
负责监听客户端发送的http请求，接收客户端发送的数据包。
设计一个队列缓存收到的数据包，
监听三个docker中的模型的状态，安排向模型输入数据。
收集模型分析数据，写入sqlite数据库。
监听前端的请求，相应地调用数据库中的数据（这部分只暴露API，不需要写复杂的Views）。


当docker内的模型都处于就绪状态时，使用http向docker发送需要分析的数据,并等待分析结果，得到分析结果后，将分析结果以及数据存入
//将模型抽象封装为一个webapp,以API调用的方式，实时监听客户端的请求（以及）

这个过程的一些小问题：
客户端向上传输的数据有图片，以及JSON格式的数据列，如何解析JSON文件？
如何实现缓存队列？
如何操作数据库？
向前端发送的数据也包含有图片以及数据列，如何将数据打包？JSON化数据




熟悉flask/django的基础开发过程
https://flask.github.net.cn/tutorial/py-modindex.html