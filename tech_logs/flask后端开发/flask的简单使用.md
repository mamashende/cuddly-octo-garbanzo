在 Flask 中，"@app." 是一个装饰器语法，用于将函数与特定的 URL 路径或 HTTP 方法相关联。这是 Flask 框架中常用的装饰器之一，用于定义路由和视图函数。

具体来说，"@app.route" 是常见的装饰器形式，它告诉 Flask 框架将下面的函数注册为一个视图函数，并将其与指定的 URL 路径关联起来。这样，当用户访问该 URL 时，Flask 将调用该视图函数来处理请求并生成响应。

以下是一个示例，展示了如何在 Flask 中使用 "@app.route" 装饰器：
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello, world!'

@app.route('/about')
def about():
    return 'About page'

if __name__ == '__main__':
    app.run()
```

在上面的示例中，"@app.route" 装饰器用于定义两个视图函数。`index()` 函数与根路径 "/" 关联，而 `about()` 函数与路径 "/about" 关联。当用户访问这些路径时，Flask 将调用相应的视图函数并返回其返回的内容。

通过使用不同的 HTTP 方法作为装饰器的参数，可以创建处理特定 HTTP 方法的视图函数。例如，"@app.route('/submit', methods=['POST'])" 可以将视图函数与路径 "/submit" 关联，并指定只有使用 POST 方法才能触发该函数。

总而言之，"@app.route" 装饰器在 Flask 中用于定义路由和视图函数之间的映射关系，使得 Flask 能够根据请求的 URL 调用相应的视图函数来处理请求并生成响应。

按照这个原理
一个简单的文件/数据接收后端服务应该是这样的：

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'upload the .png files'

from flask import request

@app.route('/upload', methods=['GET', 'POST'])
def upload_file():
    if request.method == 'POST':
        f = request.files['the_file']
        f.save('/var/www/uploads/uploaded_file.txt')
    ...
    #return 'About page'

if __name__ == '__main__':
    app.run()
```
用 Flask 处理文件上传很容易，只要确保不要忘记在你的 HTML 表单中设置 `enctype="multipart/form-data"` 属性就可以了。否则浏览器将不会传送你的文件。