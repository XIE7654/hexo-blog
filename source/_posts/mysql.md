---
title: mysql
date: 2018-12-13 15:28:31
tags:
---


mysql5.7
user表中password改为
```
authentication_string
```

bind-address 配置文件路径
```
/etc/mysql/mysql.conf.d/mysqld.cnf
```



1、Mysql语句备份一个数据库:
备份的语句mysqldump的基本语法: mysqldump -u username -p dbname table1 table2... > test.sql;

参数解析:

dbname：要备份数据库的名称；

table1和table2参数表示的是需要备份的数据库表的名称，假如为空则表示需要备份整个数据库；

test.sql表示的是将数据库备份到指定的这个.sql的文件中，这个文件的前面可以执行一个详细的绝对路径下；


2、mysql 修改表或表结构

```
alter table old_name rename new_name; --修改表名

alter table test add  column add_name varchar(10); --添加表列

alter table test drop  column del_name; --删除表列

alter table test modify address char(10) --修改表列类型
# alter table test change address address  char(40)


alter table test change  column address address1 varchar(30)--修改表列名
————————————————
```


3、外键约束
```
1. 查看数据库表创建的sql语句
show create table test

2. 查看外键的约束名
CREATE TABLE `test` (
 `id` int(11) NOT NULL AUTO_INCREMENT,
 `address` varchar(255) DEFAULT NULL,
 `code` varchar(255) DEFAULT NULL,
 `mobile` varchar(255) DEFAULT NULL,
 `name` varchar(255) DEFAULT NULL,
 `score` int(11) DEFAULT NULL,
 `id_code` varchar(255) DEFAULT NULL,
 `user_id` int(11) DEFAULT NULL,
 PRIMARY KEY (`id`),
 KEY `FK1C81D1738DA76` (`user_id`),
 CONSTRAINT `FK1C81D1738DA76` FOREIGN KEY (`user_id`) REFERENCES `user` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8

3. 解除外键约束
alter table vip drop foreign key FK1C81D1738DA76

4. 删除外键
alter table vip drop user_id

5. 增加外键约束
ALTER TABLE `tfeedbackmessage`
ADD CONSTRAINT `FK_i1q2cf5pxfr8r69cfci3yyari` FOREIGN KEY (`HANDLERID`) REFERENCES `toperationuser` (`FID`) 
ON DELETE CASCADE ON UPDATE RESTRICT;

```


常见操作小结：

查看表的字段信息：desc 表名;

查看表的所有信息：show create table 表名;

添加主键约束：alter table 表名 add constraint 主键 （形如：PK_表名） primary key 表名(主键字段);

添加外键约束：alter table 从表 add constraint 外键（形如：FK_从表_主表） foreign key 从表(外键字段) references 主表(主键字段);

删除主键约束：alter table 表名 drop primary key;

删除外键约束：alter table 表名 drop foreign key 外键（区分大小写）;
