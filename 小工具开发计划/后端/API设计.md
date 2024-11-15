```
获取所有topics
请求：GET 
路由：/todolist/topics
返回类型：list
返回内容：topic构成的list

获取topic下的所有todos
请求：GET
路由：/todolist/topics/{topicsID}
返回类型：

```

https://go.dev/doc/tutorial/web-service-gin
参考文档进行简单的设计


规范API文档，因此文档放在下面了
https://app.apifox.com/project/5084098

[[2024-08-31]]
先学习前端去了，不然没法写API文档


[[2024-09-17]]
前端繁杂，计划有变，先设计后端
```
获取所有topics
请求：GET 
路由：/todolist/topics
返回类型：list
返回内容：topic构成的list

获取topic下的所有todos
请求：GET
路由：/todolist/topics/{topicsName}
返回类型：

添加topic
POST
/todolist/AddTopic
发送格式 JSON
附加要求：topic是不能出现重复的


添加todo
POST
/todolist/AddTodo
发送格式 JSON

删除todo
DELETE
/todolist/DeleteTodo
参数 todo.title

删除topic
DELETE
/todolist/DeleteTopic
参数 topic.name

更新todo完成状态
UPDATE
/todolist/UpdateTodoStatus
参数 todo.status??//这里还没有设计完善
```