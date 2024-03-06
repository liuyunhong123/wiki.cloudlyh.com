---
title: Centos7防火墙firewalld操作
description: Centos7防火墙firewalld操作
published: true
date: 2024-03-06T11:56:52.337Z
tags: centos7
editor: markdown
dateCreated: 2024-03-04T05:52:01.644Z
---

在CentOS 7.6中，防火墙主要由firewalld服务进行管理。以下是一些常用的防火墙操作：

1. **检查防火墙状态：**

    ```
    sudo systemctl status firewalld
    ```
2. **启动/停止/重启防火墙服务：**

    ```
    sudo systemctl start firewalld
    sudo systemctl stop firewalld
    sudo systemctl restart firewalld
    ```
3. **设置防火墙开机启动：**

    ```
    sudo systemctl enable firewalld
    ```
4. **查看防火墙支持的服务：**

    ```
    firewall-cmd --get-services
    ```
5. **查看防火墙规则：**

    ```
    firewall-cmd --list-all
    ```
6. **开放端口：**

    ```
    sudo firewall-cmd --zone=public --add-port=80/tcp --permanent
    ```

    这将永久性地在公共区域打开80端口，如果需要修改其他端口，请替换`80`为相应的端口号。
7. **移除端口：**

    ```
    sudo firewall-cmd --zone=public --remove-port=80/tcp --permanent
    ```

    这将永久性地从公共区域移除80端口。
8. **重新加载防火墙配置：**

    ```
    sudo firewall-cmd --reload
    ```
9. **查看防火墙状态：**

    ```
    sudo firewall-cmd --state
    ```
10. **查看已开放的端口：**

     ```
     sudo firewall-cmd --list-ports
     ```

请注意，上述命令中的`--permanent`选项表示将更改永久性保存到防火墙配置中。在修改配置后，需要使用`--reload`重新加载防火墙。

这只是一些基本操作，具体的防火墙设置取决于你的网络环境和应用需求。确保在修改防火墙设置之前理解你的网络安全需求，以免造成安全风险。