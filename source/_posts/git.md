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



### 移除已经添加的文件（缓存区）
``` bash
使用 git rm 命令即可，有两种选择,

一种是 git rm –cached “文件路径”，不删除物理文件，仅将该文件从缓存中删除；

一种是 git rm –f “文件路径”，不仅将该文件从缓存中删除，还会将物理文件删除（不会回收到垃圾桶）。

git –如何撤销已放入缓存区（Index区）的修改
修改或新增的文件通过 git add –all命令全部加入缓存区（index区）之后，使用 git status 查看状态

（git status -s 简单模式查看状态，第一列本地库和缓存区的差异，第二列缓存区和工作目录的差异），

提示使用 git reset HEAD 来取消缓存区的修改。

不添加参数，撤销所有缓存区的修改。

另外可以使用 git rm –cached 文件名 ，可以从缓存区移除文件，使该文件变为未跟踪的状态，

同时下次提交时从本地库中删除。

注：

没有带参数的 git reset 命令，默认执行了 –mixed 参数，即用reset版本库到指定版本，并重置缓存区，在上面的命令中指定的目录版本是HEAD，即当前版本，所以实际上没有任何修改，仅是重置了缓存区。
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

### mac remote: Permission
```bash
git config credential.username XIE7654
```
