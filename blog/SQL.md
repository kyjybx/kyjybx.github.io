# sql注入

## 数据库的结构
- 连上去的库包含了多个数据库，想看套娃了哪些数据库？
```sql
show databases;     //我又不搞开发，小写是无所谓的
```
接下来就会展示包含的所有数据库，包括这个mysql自身的关键信息“库”

- 找到了想要的库，用
```sql
use 要看的库;
```

- 从库开始，就没有套娃（我指同级数据结构嵌套），会来到库的下一级，也就是表，展示表的语法和库一样
```sql
show tables;
```

- 找到到想用的表之后，需要对表的详情（有哪些列，我更喜欢称为哪些键）查看
```sql
describe 表名;
```


# 常用语句


## 注入句式
- 使用注释符
  ```mysql
  --space
  注意：在url中空格将会转译为“+”，实际没有影响
  ```

- union语句
  union select 语句需要确保左右两边键数一致，如果发现某列被遮盖，使用数字来标注

- order by语句
  order by 数值判断键数



## 运算符
- mysql等价运算：=（允许字符串类型带入）

- not 否运算，优先级低于=

- sql的二元逻辑运算从右到左

- 记一下php语法
  ```php
  $searchInput =  $_POST['findUser'];
  $query = "select * from logins where username like '%$searchInput'";  使用%格式化字符串
  $result = $conn->query($query);
  ```

- urlEncode:
> \'	&nbsp;%27
 \"	&nbsp;%22
 \#	&nbsp;%23
 \;	&nbsp;%3B
> \)	&nbsp;%29