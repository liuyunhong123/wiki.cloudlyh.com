---
title: Ubuntu20开启root用户登录
description: Ubuntu20开启root用户登录
published: true
date: 2024-03-06T11:57:34.757Z
tags: ubuntu20
editor: markdown
dateCreated: 2024-03-04T05:52:48.209Z
---

> 在 Ubuntu 22.04.3 LTS 中，root 用户默认是禁用的，这意味着您不能直接使用 root 用户登录。但是，您可以通过以下步骤启用 root 用户并设置密码：

#### 1.启用 root 用户： 打开终端（Ctrl + Alt + T），然后输入以下命令以切换到 root 用户或使用 sudo 来执行命令：

```shell
sudo -i
```

#### 2.设置 root 用户密码： 在终端中，输入以下命令来设置 root 用户的密码：

```shell
passwd root
```

> 在提示下输入您想要设置的 root 用户密码。为了安全起见，建议设置一个强密码。

#### 3.重新启动系统： 您需要重新启动系统以使更改生效。可以使用以下命令来重启系统：

```shell
reboot
```

#### 4.登录 root 用户： 重新启动后，您应该能够在登录界面看到 root 用户。输入 root 用户的密码以登录。

此外，建议定期更新系统以确保安全性，并且只在必要时使用 root 用户。