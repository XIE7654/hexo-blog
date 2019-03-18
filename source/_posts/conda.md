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
# 查看环境
conda info -e
```

```
# 创建一个名为python34的环境，指定python版本为3.4
```
conda create --name python34 python=3.4
```

# 切换环境
```
activate python34 # for Windows
source activate python34 # for Linux & Mac


```
退出环境
source deactivate
```

```

# 删除环境
```
conda remove --name python34 --all
```


# 设置镜像
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```

# 修改默认环境

在linux下，通过修改~/.bashrc或~/.bash_profile最后你会发现
```
export PATH="~/anaconda3/bin:$PATH"
```

修改为
```
export PATH="~/anacond3/envs/python3/bin:$PATH"

```
