基本语法


模型创建，记录添加
```
//模型声明，采用结构体
type Topics struct {

gorm.Model

Name string

}

  

type Todos struct {

gorm.Model

Text string

TopicID uint//自动处理外键

}

//创建数据库
db, err := gorm.Open(sqlite.Open("test.db"), &gorm.Config{})
if err != nil {

panic("failed to connect database")

}

//在数据库中创建表
db.AutoMigrate(&Topics{})

db.AutoMigrate(&Todos{})


// Create

db.Create(&Topics{Name: "learn"})

db.Create(&Topics{Name: "life"})

  

db.Create(&Todos{Text: "啊哦", TopicID: 1})

db.Create(&Todos{Text: "buy apples", TopicID: 2})

//Read

//Update

//Delete
```


注：GORM能够自动处理表中的外键，在模型声明时将其按照规定表示外键即可


查询
## 检索全部对象

|                                                                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| // Get all records  <br>result := db.Find(&users)  <br>// SELECT * FROM users;  <br>  <br>result.RowsAffected // returns found records count, equals `len(users)`  <br>result.Error        // returns error |


附带条件的查询
https://gorm.io/zh_CN/docs/query.html#%E6%9D%A1%E4%BB%B6