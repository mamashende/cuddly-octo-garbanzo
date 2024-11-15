[[2024-03-31]]
安装conda:
[Miniconda — Anaconda documentation](https://docs.anaconda.com/free/miniconda/)

使用conda管理环境：
[Managing environments — conda 24.3.1.dev23 documentation](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
由于有测试深度学习的需求，又难以应付繁杂的版本管理应用带来的各种问题，因此这里使用miniconda来管理python环境


如果是其他的测试环境的话，可以试试pyenv+pipenv实现环境管理

其实在开发环境中，最简便的方法是通过IDE如pyCharm的环境管理


正式发布的服务版本的话，还是建议使用docker容器隔离环境好了


#### pip 安装依赖时报错

#### ERROR: Could not install packages due to an OSError: [Errno 28] No space left on device
简单的解决办法：
[python - Could not install packages due to an EnvironmentError: [Errno 28] No space left on device - Stack Overflow](https://stackoverflow.com/questions/55103162/could-not-install-packages-due-to-an-environmenterror-errno-28-no-space-left)


#### 无用包清理
感觉清理得不是太干净的样子，但是也只能暂时这样了
```shell
conda clean --all
```