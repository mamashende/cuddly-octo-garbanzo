## insert
指定字段添加数据：
```sql
insert into xx_table (key0,key1,....) values (value0,value1,...);
```
全部字段添加数据：
```sql
insert into xx_table values (value0,value1,...);
```
批量添加数据（指定字段）：
```sql
insert into xx_table (key0,key1) values (value0,value1),(value0,value1);
```
批量添加数据（全部字段）：
```sql
insert into xx_table values (value0,value1,...),(value0,value1,...);
```
