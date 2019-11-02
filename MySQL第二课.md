MySQL的安装：压缩包的话需要添加my.ini配置文件，客户端的安装不用配置文件，但需要有visual studio环境

# Navicat操作数据库

## 1.数据表的导入

![img](http://a2.qpic.cn/psb?/V13HAV523S7hJj/F2.ChO2Ufj2KffTa6ImhZwQkqKv5w9FIlsZgZHgh06w!/c/dE0BAAAAAAAA&ek=1&kp=1&pt=0&bo=sARDAwAAAAADF8Y!&tl=1&vuin=2362846077&tm=1572696000&sce=60-2-2&rf=0-0)

![1572681642540](C:\Users\win10\AppData\Roaming\Typora\typora-user-images\1572681642540.png)

点击连接，选择MySQL，输入密码登陆，点击确定建立与MySQL数据库的连接

![1572681800269](C:\Users\win10\AppData\Roaming\Typora\typora-user-images\1572681800269.png)

右键点击建立的连接，选择新建数据库或从已有的数据库中选择一个，这里注意建立新数据库时字符集要选择utf8，排列顺序选择utf8_general_ci

![1572682205652](C:\Users\win10\AppData\Roaming\Typora\typora-user-images\1572682205652.png)

打开数据库，右键点击表，选择导入向导，选择相应的类型导入即可，注意编码要使用UTF-8，每一列的类型选择以够用省内存为标准

## 2.数据表中字段每一种类型及约束的意义

### 数值类型

![img](http://m.qpic.cn/psb?/V13HAV523S7hJj/nJ.cQlGvyYe0356dGtL2HHV9knfs2dvUgZv7HbQSV8Y!/b/dLYAAAAAAAAA&bo=jQIDAQAAAAADB68!&rf=viewer_4)

### 字符串类型

![img](http://a4.qpic.cn/psb?/V13HAV523S7hJj/CCzDahBdxbzMzMY1LcLhYwxPZFVyf8gC6lfP7jA6UF8!/m/dFMBAAAAAAAAnull&bo=hwIoAQAAAAADB44!&rf=photolist&t=5)

注意： char 和 varchar 需要指定长度 

### 时间日期类型

https://files.jb51.net/file_images/article/201512/20151216143817755.png?20151116143826

### 特殊类型

枚举：enum，只能在所给选项中选择

注意：存图片、音频、视频时通常只存路径，如网站常采取云存储的方式

### 常见约束

**主键**(primary key) :

是表中的一个或多个字段，它的值用于惟一地标识表中的某一条记录。一个表不能有多个主关键字，并且主关键字的列不能包含空值和重复值。主关键字是可选的，并且可在 CREATE TABLE 或 ALTER TABLE 语句中定义。 

主键不应包含动态变化的数据，如时间戳、创建时间等
主键应当由系统自动生成 

**非空**(not null): 

因为逻辑上的一些要求，有时候需要把字段属性设置为非空（NOT NULL），如记录用户名、密码等非空值的字段。
设置为非空的列，虽然不是必须，但最好设定一个默认值，以防止意外的错误和减少增加数据时的 SQL 语句复杂度。当向数据表增加数据记录时，如果设置为非空的字段不写入数据，系统将会以默认值写入。 

**自动递增**(auto_increment):

将该字段设置为 int 类的数据类型，每向数据表添加一条记录，该字段的值会自动加1 。设置了自动递增后，该列不用再设置默认值和唯一性约束。 

**外键**(foreign key):

在两个表的关系中，当一张表（如表A ）的主关键字被包含在另一张表（如表B）中时，A 表中的主关键字便成为 B 表的外键（外关键字）。B 表称为主表，A 表称为从表。

外键主要用于保持数据一致性，完整性，避免冗余数据，使两张或多张表形成关联。

当为关系字段填写值时，会到关联的表中查询此值是否存在，如果存在则填写成功，如果不存在，则填写失败并抛出异常。

注意：外键约束可以保证数据的有效性，但在进行数据的curd(增删改查)时，则会降低数据库的性能

**默认值**(default):

不填写此值时会使用默认值，如果填写则以填写的值为准

**唯一性约束**(unique)：

此字段添加的值是不允许重复的

**索引**(key):

数据库索引（index）是为了增加查询速度而对字段附加的一种标识。我们对表的某些可能需要经常查询的字段建立适当的索引，那么在查询该字段数据时，便会显著的加快查询速度。 
