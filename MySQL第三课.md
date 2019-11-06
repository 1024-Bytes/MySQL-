# 对数据库的基本操作

## 1.查看所有数据库

```mysql
show databases;
```

## 2.使用数据库

```mysql
use 数据库名;
```

## 3.查看当前使用的数据库

```mysql
select database();
```

## 4.查看创建数据库的语句

```mysql
show create database 数据库名;
```

## 5.创建数据库

```mysql
create database 数据库名 charset=utf8;
```

## 6.删除数据库

```mysql
drop database 数据库名;
```

#  对数据表的基本操作

## 1.查看当前数据库中所有数据表

```mysql
show tables;
```

## 2.创建数据表

```mysql
create table 数据表名(字段 类型 约束,字段 类型 约束);
create table class_students(
    id int primary key not null auto_increment,
    name varchar(30),
    age tinyint unsigned default 0,
    high decimal(5,2),
    gender enum('男'，'女') default '保密',
    cls_id int unsigned
);
create table classes(
    id int unsigned not null auto_increment primary key,
    name varchar(30)
);
```

**注**：SQL语句可以换行，unsigned可作为一种约束，意为只能为正(无符号)。

## 3.查看表的结构

```mysql
desc 数据表名;
```

## 4.插入一行数据

```mysql
insert into 数据表名 values(字段1,字段2);
insert into class_students(0,'小明',18,180.30,'男',1);
insert into classes(0,'一班');
```

## 5.查看表的全部数据

```mysql
select * from 数据表名;
```

## 6.修改表的结构

### 添加字段

```mysql
alter table 数据表名 add 字段名 类型;
alter table class_students add birthday datetime;
```

### 修改字段

**不重命名**：

```mysql
alter table 表名 modify 列名 类型 约束;
alter table class_students birthday date;
```

**重命名**：

```mysql
alter table 表名 change 原名 新名 类型 约束;
alter table class_students change birthday birth  date default '2000-01-01'; 
```

### 删除字段

```mysql
alter table 表名 drop 字段名;
alter table class_students drop birthday;
```

## 7.删除表

```mysql
drop table 数据表名;
```

## 8.查看创建数据表的语句

```mysql
show create table 数据表名;
```

