---
title: conda
date: 2018-12-13 10:56:05
tags:
---


# ubuntu安装conda

```
wget https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh
bash Anaconda3-4.4.0-Linux-x86_64.sh
```
# 如果在安装的过程中输入了yes，应该就直接安装成功了，不用再看下面的内容
# 关于手动修改环境变量：
```
vi ~/.bashrc
```
# 在bashrc文件的最后添加：export PATH="/home/用户名/anaconda3/bin:$PATH"。（vi编辑器中按i进入编辑模式）
```
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
# 退出环境
# source deactivate
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
