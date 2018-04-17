---
title: git
date: 2018-04-13 19:16:12
tags:
---
### The file will have its original line endings in your working directory.

``` bash
git rm -r --cached ./
git config core.autocrlf false
git add ./
```

### 添加远程仓库
``` bash
git remote add origin git@github.com:XIE7654/XIE7654.git
```
把上面的XIE7654替换成你直接的github帐户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。
添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。
下一步，就可以把本地库的所有内容推送到远程库上：
``` bash
git push -u origin master
```