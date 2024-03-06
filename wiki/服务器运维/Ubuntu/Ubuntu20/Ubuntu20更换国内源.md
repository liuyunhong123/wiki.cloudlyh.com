---
title: Ubuntu 20.04更换国内源
description: Ubuntu 20.04更换国内源
published: true
date: 2024-03-06T11:57:37.620Z
tags: ubuntu20
editor: markdown
dateCreated: 2024-03-04T05:52:52.159Z
---

我们在[Ubuntu](https://so.csdn.net/so/search?q=Ubuntu&spm=1001.2101.3001.7020)中常常遇到下载东西非常缓慢,这时如果网络没有问题,那一般就是源的问题,Ubuntu内置国外源,下载东西速度比较慢.以下是更换源的流程

### 首先需要备份原来的源

快捷键打开终端方式Ctrl+Alt+T.或鼠标右键打开终端.

```shell
sudo cp /etc/apt/sources.list /etc/apt/sources_init.list
```

这里是备份源代码.

### 更换源

```shell
sudo gedit /etc/apt/sources.list
```

这里可将原来的源全部删除,然后复制粘贴换上阿里源,网易源等国内源.并保存.

```shell
deb https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse

# deb https://mirrors.aliyun.com/ubuntu/ jammy-proposed main restricted universe multiverse
# deb-src https://mirrors.aliyun.com/ubuntu/ jammy-proposed main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse

```

### 更新源

```shell
sudo apt-get update
```

更新软件

```shell
sudo apt-get upgrade
```

然后就大功告成!!!

### 以下是几个常用源

### 1.阿里源

```shell
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

```

### 网易源

```shell
deb http://mirrors.163.com/ubuntu/ wily main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ wily-security main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ wily-updates main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ wily-proposed main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ wily-backports main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ wily main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ wily-security main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ wily-updates main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ wily-proposed main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ wily-backports main restricted universe multiverse


```

国内其他源地址
1.豆瓣 http://pypi.douban.com/simple/
2.中国科学技术大学http://pypi.mirrors.ustc.edu.cn/simple/
3.清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/