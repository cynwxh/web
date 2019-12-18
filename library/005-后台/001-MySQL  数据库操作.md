# php开发 
> 简单、使用广泛、便于后期工作合作

LAMP= 开发环境
* Linux 操作系统 开源
* Apache 提供http服务 开源
* MySQL 数据库 开源
* PHP 脚本语言 开源

WAMP= 开发环境  
* WAMP(软件)集成开发环境 快速搭建开发环境
* windows 操作系统
* Apache 提供http服务 开源
* MySQL 数据库 开源
* PHP 脚本语言 开源


MAMP= 开发环境
* MAC OS
* Apache 提供http服务 开源
* MySQL 数据库 开源
* PHP 脚本语言 开源


=======================================

# MySQL 数据库 存储数据

> MySQL是一个关系型数据库管理系统，是甲骨文旗下的一款数据库。

##### MySQL


* 社区版 开源、免费
* 商业版 收费
* 5.6、5.7、8.0


##### 数据库操作语言
* DML CURD 对数据库表中的数据进行增删改查的语言 select update insert delete
* DDL 对数据库的表进行操作 create alter drop
* DCL 对数据库进行控制的语言


* 对数据的四种操作：增删改查(CURD)
    * 创建(Create)
    * 更新(Update)
    * 读取(Retrieve)
    * 删除(Delete)


* 数据库的三种关系
    * 库 存储各种表
    * 表 存储相关数据
    * 链 表与表之间的关系


--------------------------------------------

##### 数据库文件 两种
* .frm(结构) .myd(记录) .myi(索引) 
* .frm .ibd ()

### 数据库操作

#### 命令行，需要配置环境变量
#### 图形界面

### 登录mysql

* mysql -u root -p
* mysql -u root -p 123;
* mysql -u root -p --default-character-set=utf8

* show databases 显示数据库的列表
* create database 数据库名 创建数据库
* create database 数据库名 character set utf8; 创建数据库
* drop database 数据库名 删除数据库


* use 数据库名 选中数据库
* select database() 查看当前选中数据库名称


* show tables 显示当前数据库中的表
* desc 表名称 显示表结构


* select version() 显示当前mysql版本
* select now() 显示当前时间


## 导入/导出数据库
### 导出数据库
```
D:/mysqldump -u root -p --default-character-set=utf8 数据库名 > 文件名.sql
```

### 导入数据库
1. 创建数据库
```
mysql> create database book_test;
```
2. 选中这个数据库
```
mysql> use book_test;
```
3. 导入数据库
```
mysql> source 要导入数据库文件路径
mysql> source d:/desktop/book2_6.sql
```

创建表

```
create table users(
    id int(4) not null primary key auto_increment,
    name char(20) not null,
    age int(4) not null);
```


--------------------------------------
# DML
### insert操作 插入

```
<!--插入一行数据-->
insert into 表名(f1,f2,f3)value(v1,v2,v3)

<!--简写,列的数据必须写全-->
insert into 表名 values(v1,v2,v3)

<!--同时插入多行数据-->
insert into 表名(f1,f2,f3)value(v1,v2,v3),(v11,v12,v13)
```