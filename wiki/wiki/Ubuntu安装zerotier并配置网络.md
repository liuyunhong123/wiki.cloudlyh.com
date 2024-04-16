---
title: Ubuntu安装zerotier并配置网络
description: Ubuntu安装zerotier并配置网络
published: true
date: 2024-04-16T04:17:05.048Z
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

## 3.这里是虚拟内网的ID
![zerotier虚拟内网id.png](/wiki/wiki/zerotier虚拟内网id.png)

## 4.设置IP
加入自己的网络后会新增一个设备，可以设置IP或者删除IP，最左边记得打钩，不然不会生效
![zerotier虚拟内网ip.png](/wiki/wiki/zerotier虚拟内网ip.png)


