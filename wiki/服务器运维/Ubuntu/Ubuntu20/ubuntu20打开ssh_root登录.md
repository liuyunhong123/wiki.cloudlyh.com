---
title: ubuntu20打开ssh root登录
description: ubuntu20打开ssh root登录
published: true
date: 2024-03-06T11:57:44.865Z
tags: ubuntu20, ssh
editor: markdown
dateCreated: 2024-03-04T05:53:01.925Z
---

在Ubuntu 20.04中，如果您想要开启SSH服务并允许root用户登录，可以按照以下步骤操作：

1. **安装SSH服务**：首先确保您的系统中已经安装了OpenSSH Server。如果没有安装，可以通过以下命令安装：

    ```bash
    sudo apt update
    sudo apt install openssh-server
    ```
2. **配置SSH服务**：默认情况下，root用户是可以使用SSH登录的，但出于安全考虑，建议您不要直接使用root用户登录。如果您确实需要使用root用户登录，可以通过编辑`/etc/ssh/sshd_config`文件来允许root登录。使用`sudo nano /etc/ssh/sshdconfig`命令打开文件，找到`PermitRootLogin`这一行，将其改为`PermitRootLogin yes`。保存并关闭文件。
3. **重启SSH服务**：修改配置文件后，需要重启SSH服务以使更改生效。使用以下命令重启SSH服务：

    ```bash
    sudo systemctl restart sshd
    ```
4. **检查SSH服务状态**：为了确保SSH服务正在运行，可以使用以下命令检查其状态：

    ```bash
    systemctl status sshd
    ```
5. **设置防火墙规则**：如果您的系统正在运行UFW防火墙，确保已经允许SSH服务通过。可以使用以下命令来允许SSH服务：

    ```bash
    sudo ufw allow ssh
    ```
6. **更新源**：为了确保软件包的更新速度，建议您将软件包源更改为国内的镜像源，如阿里云。您可以通过编辑`/etc/apt/sources.list`文件来实现这一点，或者使用图形界面的“软件和更新”来选择国内的源。
    完成以上步骤后，您的Ubuntu 20.04系统应该已经成功开启了SSH服务，并允许root用户通过SSH登录。请确保在进行此类操作时遵循最佳的安全实践，以保护您的系统和数据安全。