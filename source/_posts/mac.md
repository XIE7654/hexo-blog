---
title: mac
date: 2018-05-23 15:00:57
tags:
---

### 查看端口占用
```bash
lsof -i tcp:3000
```

关闭端口
``` bash
kill -9 6806(查到的PID号)
```

### MAC可能在设置环境变量的时候设置错了，现在整个MAC的vi，ls等命令都执行不了了

在命令行中输入
```
export PATH=/usr/bin:/usr/sbin:/bin:/sbin:/usr/X11R6/bin
```
这样可以保证命令行命令暂时可以使用。命令执行完之后先不要关闭终端
或者
```
cd /usr/bin
```
下执行vi命令

恢复bash_profile文件
```
vi ~/.bash_profile
```
很有可能是你的PATH 环境变量设置错误

立即生效，
```
source ~/.bash_profile
```
