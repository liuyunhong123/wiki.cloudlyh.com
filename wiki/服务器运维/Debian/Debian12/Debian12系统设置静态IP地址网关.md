---
title: Debian12系统设置静态IP地址网关
description: Debian12系统设置静态IP地址网关
published: true
date: 2024-03-06T11:57:13.496Z
tags: debian12
editor: markdown
dateCreated: 2024-03-04T05:52:19.756Z
---

首选备份原始的网络配置文件

```
cp /etc/network/interfaces  /etc/network/interfacesbak
```

编辑文件 /etc/network/interfaces，内容如下：

```
auto lo
auto eth0  #设置开机自动连接网络
 
iface lo inet loopback
 allow-hotplug eth0
 iface eth0 inet static   #static表示使用固定IP地址上网，dhcp表示使用动态ip
 address 192.168.9.100    #设置静态ip地址
 netmask 255.255.255.0   #子网掩码
 gateway 192.168.9.254    #网关
```

```
auto lo
auto eth0
 
iface lo inet loopback
 allow-hotplug eth0
 iface eth0 inet static
 address 192.168.9.100
 netmask 255.255.255.0
 gateway 192.168.9.254
```

**配置Debian环境中的** **[DNS](https://www.debian.cn/tag/dns/)** **服务器**

这个配置过程与Redhat 系列的系统是相同的，只需要修改 /etc/resolv.conf 文件即可，内容如下：

```
nameserver 114.114.114.114   #设置首选dns
nameserver 8.8.8.8   #设置备用dns
```

至此，IP地址、网关、DNS配置完成。

**重启网络使配置生效：**

```
systemctl restart networking
```

检查新配置是否工作：

```
ping www.debian.cn
```

如果重启网络后，配置并没有生效，请检查是否有书写错误，比如全角和半角字符。interfaces 文件中 "auto eth0" 也很关键， /etc/init.d/networking 根据这个字段判断是否启动某个网卡的网络