---
title: conda
date: 2018-12-13 10:56:05
tags:
---


# ubuntu安装conda

```
wget https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh
bash Anaconda3-4.4.0-Linux-x86_64.sh
vi ~/.bashrc
source ~/.bashrc

```

# 创建一个名为python34的环境，指定python版本为3.4
```
conda create --name python34 python=3.4
```

# 切换环境
```
deactivate python34 # for Windows
source deactivate python34 # for Linux & Mac
```

# 删除环境
```
conda remove --name python34 --all
```


# 设置镜像
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```
