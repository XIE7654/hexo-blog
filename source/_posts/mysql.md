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
