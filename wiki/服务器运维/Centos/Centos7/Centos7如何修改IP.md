---
title: Centos7如何修改IP
description: Centos7
published: true
date: 2024-03-06T11:56:46.987Z
tags: centos7
editor: markdown
dateCreated: 2024-03-04T05:51:56.783Z
---

在CentOS 7中修改IP地址，通常有以下几种方法：
### 方法一：使用`nmtui`命令
1. 打开终端。
2. 输入`nmtui`命令并回车。
3. 使用方向键选择“Edit a connection”。
4. 选择你需要修改的连接，通常是以`eth0`、`eno1`等命名的。
5. 修改IPv4 CONFIGURATION中的“Automatic”为“Manual”。
6. 添加或修改IP地址、子网掩码、网关等信息。
7. 保存并退出。
### 方法二：直接编辑网络配置文件
1. 打开终端。
2. 使用`cd /etc/sysconfig/network-scripts/`命令切换到网络配置文件所在的目录。
3. 使用`vi ifcfg-<interface_name>`命令编辑对应的网络接口配置文件，其中`<interface_name>`是你的网络接口名，如`eth0`、`eno1`等。
4. 修改或添加以下内容：
    - `BOOTPROTO=static` # 静态IP
    - `IPADDR=<你的IP地址>` # 例如192.168.1.100
    - `NETMASK=<子网掩码>` # 例如255.255.255.0
    - `GATEWAY=<网关地址>` # 例如192.168.1.1
    - `ONBOOT=yes` # 开机启动
5. 保存并退出`vi`编辑器。
6. 重启网络服务：`systemctl restart network`
### 方法三：使用`nmcli`命令
1. 打开终端。
2. 使用`nmcli con mod <connection_name> ipv4.addresses <IP地址>/<子网掩码>`命令来添加IP地址，例如：`nmcli con mod eth0 ipv4.addresses 192.168.1.100/24`。
3. 使用`nmcli con mod <connection_name> ipv4.gateway <网关地址>`命令来设置网关，例如：`nmcli con mod eth0 ipv4.gateway 192.168.1.1`。
4. 使用`nmcli con mod <connection_name> ipv4.method manual`命令设置为手动配置。
5. 使用`nmcli con up <connection_name>`命令来激活连接。
### 注意事项：
- 在修改网络配置时，请确保你有足够的权限。
- 修改网络配置后，请检查网络连接是否正常。
- 如果你的服务器有防火墙或安全组设置，可能需要更新规则以允许新的IP地址。
以上就是在CentOS 7中修改IP地址的几种常见方法，请根据实际情况选择合适的方法。
