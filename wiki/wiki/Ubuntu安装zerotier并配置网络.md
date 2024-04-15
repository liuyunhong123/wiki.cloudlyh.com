---
title: Ubuntu安装zerotier并配置网络
description: Ubuntu安装zerotier并配置网络
published: true
date: 2024-04-15T04:55:17.175Z
tags: ubuntu20, zerotier
editor: markdown
dateCreated: 2024-04-15T04:49:41.784Z
---

## 1.Ubuntu下载zerotier
zerotier下载链接：
```
curl -s https://install.zerotier.com | sudo bash
```
> 如果已经是root用户登录，那么不需要加“`sudo`”
{.is-warning}

## 2.加入局域网
```
zerotier-cli join xxxxxxxxxxxxx
```

## 3.

