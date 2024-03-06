---
title: centos7配置内网网卡静态IP192.168.10.1
description: centos7配置内网网卡静态IP192.168.10.1
published: true
date: 2024-03-06T11:56:58.682Z
tags: centos7, 网卡
editor: markdown
dateCreated: 2024-03-04T05:52:05.557Z
---

在CentOS 7中配置内网网卡的静态IP地址，您需要编辑网卡的配置文件。以下是一个基本的步骤指南：
1. 打开终端。
2. 使用以下命令备份当前的网络配置文件（以防万一）：
   ```sh
   cp /etc/sysconfig/network-scripts/ifcfg-<INTERFACE> /etc/sysconfig/network-scripts/ifcfg-<INTERFACE>.bak
   ```
   其中`<INTERFACE>`是您要配置的网络接口名称，如`eth0`或`ens33`等。
3. 编辑网络接口的配置文件：
   ```sh
   vi /etc/sysconfig/network-scripts/ifcfg-<INTERFACE>
   ```
   或者使用您喜欢的文本编辑器。
4. 在这个文件中，您需要设置或修改以下参数：
   ```sh
   BOOTPROTO=static
   ONBOOT=yes
   IPADDR=192.168.10.1
   NETMASK=255.255.255.0
   GATEWAY=192.168.10.254
   DNS1=192.168.10.254
   ```
   其中：
   - `BOOTPROTO`设置为`static`表示使用静态IP地址。
   - `ONBOOT`设置为`yes`确保网络服务启动时激活该接口。
   - `IPADDR`是您想要设置的静态IP地址。
   - `NETMASK`是子网掩码。
   - `GATEWAY`是网关地址。
   - `DNS1`是首选的DNS服务器地址。
5. 保存并关闭文件。
6. 重启网络服务以应用更改：
   ```sh
   systemctl restart network
   ```
7. 您可以使用`ip addr`命令来验证IP地址是否已经设置成功。
8. 如果您需要配置多个IP地址，或者有更高级的配置需求，您可能还需要编辑`/etc/sysconfig/network`文件。
请注意，如果您是在一个复杂的网络环境中，或者您不熟悉网络配置，请确保在进行更改之前咨询网络管理员或专业人士，以避免造成网络服务中断。此外，如果您是在公司或组织内部进行配置，请确保遵守相关的网络安全政策和指导原则。
