---
title: ubuntu20.04设置自动同步时间
description: ubuntu20.04设置自动同步时间
published: true
date: 2024-09-27T13:09:06.878Z
tags: ubuntu20
editor: markdown
dateCreated: 2024-09-27T12:18:42.951Z
---

# ubuntu20.04
## 1.首先使用命令date发现时间不对
```
date
```
![01.date时间不正确.png](/wiki/wiki/ubuntu20设置自动同步时间/01.date时间不正确.png)

## 2.查看当前时区
```
timedatectl
```
![02.查看当前时区.png](/wiki/wiki/ubuntu20设置自动同步时间/02.查看当前时区.png)

## 3.设置时区为北京上海
```
timedatectl set-timezone Asia/Shanghai
```
![03.设置时区为北京上海.png](/wiki/wiki/ubuntu20设置自动同步时间/03.设置时区为北京上海.png)

## 4.使用以下命令查看 chrony 的同步状态：
```
chronyc sources
```
![04.查看当前同步时间.png](/wiki/wiki/ubuntu20设置自动同步时间/04.查看当前同步时间.png)
发现Reach没有变换，说明同步失败的

