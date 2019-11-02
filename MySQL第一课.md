# 1.RDBMS（关系型数据库管理系统）

## 数据库介绍

数据库主要分为关系型数据库和非关系型数据库，MySQL（开源）一般用来做网站,存一些持久保存的数据，Redis一般用于缓存，MongoDB用于存储非关系型数据库结构，一般可以爬虫用。

## 数据库的操作原理

<img src="C:\Users\win10\AppData\Roaming\Typora\typora-user-images\1572678548189.png" style="zoom:67%;" />

这是一种C-S架构模型，RDBMS-server可以直接管理数据库，MySQL就是一种RDBMS-server，浏览器和服务器之间通常通过http协议来通信，而上面的例子则通过SQL语句通信。

### 两种架构

#### C-S架构

app就是C-S架构模式

#### B-S架构

B-S就是通过浏览器操作网页

## SQL

一种结构化查询语言，是可以操作RDBMS的数据库语言

不区分大小写

支持很多种数据库，如Oracle，MySQL，MS SQL server,SQLITE

**DQL**：数据查询语言，用于对数据进行查询，如select

**DML**：数据操作语言，对数据进行增加、修改、删除，如insert、update、delete

TPL ：事务处理语言，对事务进行处理，包括begin transaction、commit、rollback

DCL：数据控制语言，进行授权与权限回收，如grant、revoke

DDL：数据定义语言，进行数据库、数据表的管理等，如create、drop

CCL：指针控制语言，通过控制指针完成表的操作，如declare cursor

