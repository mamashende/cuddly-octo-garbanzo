新增套餐的SQL语句
```sql
insert into setmeal (id,category_id,name,price,status,description,image,create_time,update_time,create_user,update_user) values (#{id},#{categoryId},#{name},#{price},#{status},#{descripton},#{image},#{createTime},#{updateTime},#{createUser},#{updateUser})
```
这里的各个键值对的顺序问题应该不会有太大的影响

修改：去掉id，因为是主键自增
```sql
insert into setmeal (category_id,name,price,status,description,image,create_time,update_time,create_user,update_user) values (#{categoryId},#{name},#{price},#{status},#{descripton},#{image},#{createTime},#{updateTime},#{createUser},#{updateUser})
```