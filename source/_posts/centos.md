---
title: centos
date: 2018-05-24 15:47:01
tags:
---

centos关闭防火墙

### 关闭命令：
``` bash
service iptables stop
```

### 永久关闭防火墙：
``` bash
chkconfig iptables off
```

### 两个命令同时运行，运行完成后查看防火墙关闭状态：
``` bash
service iptables status
```

### 关闭防火墙：
``` bash
service iptables stop
```

### 启动防火墙：
``` bash
service iptables start
```

### 重启防火墙：
``` bash
service iptables restart
```

### 查看防火墙状态：
``` bash
service iptables status
```


### 永久关闭防火墙：
``` bash
chkconfig iptables off
```

### 永久关闭后启用：
``` bash
chkconfig iptables on
```