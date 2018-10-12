---
title: python
date: 2018-09-03 20:58:58
tags:
---

自己写了一个python脚本，但是直接远程用putty连接后#python xxx.py执行，关闭putty脚本也随之关闭了，这里需要用到‘setsid’这个命令。

```bash
#setsid python xxx.py
```
如此即可将脚本加入到后台执行
若想查看所有后台运行的进程
```bash
#ps -aux
```
这里可以看到每个进程都有一个PID，如果想杀死这个进程，则使用

```bash
#kill -9 [PID]
-9 表示强迫进程立即停止
```


安装Anaconda3
```bash
wget https://repo.continuum.io/archive/Anaconda3-5.2.0-Linux-x86_64.sh
```

使环境变量生效
```bash
source ~/.bashrc
```
