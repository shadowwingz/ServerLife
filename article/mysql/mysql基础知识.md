## 登录 MySQL

```
// 登录mysql
// mysql -u(user) root -p(password)
mysql -u root -p
// 使用mysql数据库
use mysql
```

## 数据库相关操作

查看所有数据库：

```
show databases;
```

直接创建一个数据库，如果数据库已存在，会创建失败。

```
create database 数据库名称;
```

创建数据库，创建之前会先判断数据库是否存在，如果不存在，才创建。

```
create database if not exists 数据库名称;
```

直接删除数据库：

```
drop database 数据库名称;
```

删除数据库，删除之前会先判断数据库是否存在，如果存在，才删除。

```
drop database if exists 数据库名称;
```

使用某一个数据库：

```
use 数据库名称
```

查看当前正在使用的数据库：

```
select database();
```

## 查询表

查看数据库中某一个表的结构：

```
desc func;
```

## 练习题：创建一个学生表

1. 编号
2. 姓名，姓名最长不超过 10 个汉字
3. 性别，因为取值只有两种可能，因此最多一个汉字
4. 生日，取值为年月日
5. 入学成绩，小数点后保留两位
6. 邮件地址，最大长度不超过 64
7. 家庭联系电话，不一定是手机号码，可能会出现 `-` 等字符
8. 学生状态（用数字表示，正常、休学、毕业）

```
create table student(
    id int,
    name varchar(10),
    gender char(1),
    birthday date,
    score double(6,2),
    email varchar(64),
    tel varchar(15),
    status tinyint
);
```

## 修改表

修改表名

```
alter table 旧表名 rename to 新表名;
```

新增列：

```
alter table 表名 add 列名 数据类型;
```