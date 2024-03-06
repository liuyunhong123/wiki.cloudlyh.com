---
title: Debian12打开GUI的root登录
description: Debian12打开GUI的root登录
published: true
date: 2024-03-06T11:57:03.239Z
tags: debian12
editor: markdown
dateCreated: 2024-03-04T05:52:10.387Z
---

1. #### 普通用户切换root用户

    ```shell
    su -root
    ```

2. #### 更改配置文件

    ```shell
    vi /etc/gdm3/daemon.conf
    ```

    在 security 下面添加 AllowRoot=true
    保存后退出vi

3. #### 编辑文件gdm-password

    ```shell
    vi /etc/pam.d/gdm-password
    ```

    注释掉这一行 ：

    > auth required pam_succeed_if.so user != root quiet_success
    >


    #auth required pam_succeed_if.so user != root quiet_success
    保存后退出vi

4. #### 重新以root登录即可