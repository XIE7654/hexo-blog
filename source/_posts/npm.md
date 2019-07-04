---
title: npm
date: 2019-07-04 15:58:00
tags:
---


npm publish 的时候会把项目目录里面所有的文件都publish到npm仓库中，
 但是往往有一部分目录和文件不想发布上去，比如项目的源码、编译脚本等等信息。
 如何发布用户需要使用的相关文件呢？
### 方法一：
 使用 .gitignore 设置忽略哪些文件.gitignore 设置的忽略文件，
 在git代码管理和 npm publish 都会被忽略
### 方法二：
 使用 .npmignore 设置忽略哪些文件.npmignore 的写法跟 .gitignore 的规则完全一样。
 若同时使用了 .npmignore 和 .gitignore，只有 .npmignore 会生效，优先级比较高。
### 方法三：
使用 package.json 的 files 字段选择发布哪些文件直接在 package.json 中 files 字段设置发布哪些文件或目录。这个优先级高于 .npmignore 和 .gitignore。

