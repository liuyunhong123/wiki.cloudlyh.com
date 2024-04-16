---
title: Ubuntu安装zerotier并配置网络
description: Ubuntu安装zerotier并配置网络
published: true
date: 2024-04-16T04:36:33.509Z
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

## 5.本地网卡变化
打开win10的网卡设置会发现多了一个虚拟网卡，并自动配置了你在zerotier平台设置的内网IP
（如果没有自动配置可以手动配置一下，一般情况都是自动配置好的）
![zerotier本地win10网卡.png](/wiki/wiki/zerotier本地win10网卡.png)

## 6.测试连接
家里的计算机内网IP：192.168.10.2
![zerotier虚拟内网ip家里.png](/wiki/wiki/zerotier虚拟内网ip家里.png)

公司的计算机内网IP：192.168.10.3
![zerotier虚拟内网ip公司.png](/wiki/wiki/zerotier虚拟内网ip公司.png)

测试延时：平均11ms（延时非常低，公司是电信1000Mbps，家里是电信500Mbps）
![zerotier虚拟内延时测试.png](/wiki/wiki/zerotier虚拟内延时测试.png)

## 7.有条件可以自己搭建中转服务器

## 8.路由自定义
（很简单，都是有提示怎么设置的，这里就不详细写了）
![zerotier路由自定义.png](/wiki/wiki/zerotier路由自定义.png)

## 9.zerotier是一个国外的开源项目，很厉害，支持5大系统。
官方下载地址：https://www.zerotier.com/download/
官方下载地址截图：
![zerotier.png](/wiki/wiki/zerotier.png)
