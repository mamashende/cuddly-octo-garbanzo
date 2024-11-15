[使用SQLite - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/1016959663602400/1017801751919456)
GPT给出的一个简单样例：

要实现 Flask 接收客户端发送的 JSON 数据，解析后写入 SQLite 数据库，可以按照以下步骤进行操作：

1. 安装所需的库：确保你已经安装了 Flask 和 SQLite 相关的库。可以使用以下命令进行安装：

   ```
   pip install flask
   ```

2. 创建 Flask 应用程序：创建一个简单的 Flask 应用程序，并设置一个接收 JSON 数据的路由。在路由处理函数中，获取 JSON 数据并进行解析。

   ```python
   from flask import Flask, request
   import sqlite3
   import json

   app = Flask(__name__)

   @app.route('/data', methods=['POST'])
   def process_data():
       json_data = request.get_json()

       if json_data:
           # 解析 JSON 数据
           data = json.loads(json_data)

           # 将数据写入 SQLite 数据库
           conn = sqlite3.connect('database.db')
           cursor = conn.cursor()

           # 假设数据库中有一个名为 "users" 的表，包含 "name" 和 "age" 两列
           query = "INSERT INTO users (name, age) VALUES (?, ?)"
           cursor.execute(query, (data['name'], data['age']))

           conn.commit()
           conn.close()

           return 'Data inserted successfully'
       else:
           return 'No JSON data received'

   if __name__ == '__main__':
       app.run()
   ```

   在上述示例中，我们创建了一个 `/data` 路由，使用 POST 方法接收客户端发送的 JSON 数据。首先，我们使用 `request.get_json()` 方法获取 JSON 数据。然后，我们使用 `json.loads()` 方法解析 JSON 数据，得到一个 Python 字典。

   接下来，我们连接 SQLite 数据库，执行插入操作将数据写入数据库。在这个示例中，我们假设数据库中有一个名为 "users" 的表，包含 "name" 和 "age" 两列。我们使用 SQL 语句和参数化查询来插入数据。

   最后，我们返回一个成功插入数据的消息。

3. 运行应用程序：保存上述代码为 `app.py` 文件，并运行该文件。Flask 应用程序将在本地主机上的默认端口（通常为 5000）上运行。

现在，你可以使用任何发送 JSON 数据的客户端工具（如 cURL、Postman 等）来向 `/data` 路由发送 POST 请求，并将 JSON 数据作为请求体发送。Flask 应用程序将接收并解析 JSON 数据，并将其写入 SQLite 数据库中。

请注意，在实际应用中，你可能需要进行错误处理、数据验证、数据库表的创建等更多的操作。此示例仅供参考，你可以根据自己的需求进行修改和扩展。



一个最简单的响应前端请求：
要实现 Flask 响应前端请求，并发送数据库中指定的数据和文件，你可以按照以下步骤进行操作：

1. 安装所需的库：确保你已经安装了 Flask 和 SQLite 相关的库。可以使用以下命令进行安装：

   ```python
   pip install flask
   ```

2. 创建 Flask 应用程序：创建一个简单的 Flask 应用程序，并设置一个路由来处理前端请求。在路由处理函数中，从数据库中获取指定的数据，并将文件作为响应发送给前端。

   ```python
   from flask import Flask, send_file
   import sqlite3

   app = Flask(__name__)

   @app.route('/data/<int:data_id>', methods=['GET'])
   def get_data(data_id):
       # 连接 SQLite 数据库
       conn = sqlite3.connect('database.db')
       cursor = conn.cursor()

       # 假设数据库中有一个名为 "data" 的表，包含 "id" 和 "file_path" 两列
       query = "SELECT file_path FROM data WHERE id = ?"
       cursor.execute(query, (data_id,))
       result = cursor.fetchone()

       if result:
           file_path = result[0]
           conn.close()
           return send_file(file_path, as_attachment=True)
       else:
           conn.close()
           return 'Data not found'

   if __name__ == '__main__':
       app.run()
   ```

   在上述示例中，我们创建了一个 `/data/<int:data_id>` 路由，使用 GET 方法来获取指定 `data_id` 的数据。我们连接 SQLite 数据库，执行查询操作来获取数据库中的文件路径。然后，我们使用 `send_file()` 函数将文件作为响应发送给前端。

   假设数据库中有一个名为 "data" 的表，包含 "id" 和 "file_path" 两列。我们使用 SQL 语句和参数化查询来获取指定 `data_id` 的文件路径。

   最后，我们使用 `send_file()` 函数将文件作为响应发送给前端。`as_attachment=True` 参数用于将文件作为附件下载。

3. 运行应用程序：保存上述代码为 `app.py` 文件，并运行该文件。Flask 应用程序将在本地主机上的默认端口（通常为 5000）上运行。

现在，你可以在前端发起 GET 请求到 `/data/<data_id>` 路由，其中 `<data_id>` 是你要获取的特定数据的 ID。Flask 应用程序将从数据库中获取指定的文件路径，并将文件作为响应发送给前端。

请注意，在实际应用中，你可能需要进行错误处理、数据验证、文件路径的处理等更多的操作。此示例仅供参考，你可以根据自己的需求进行修改和扩展。