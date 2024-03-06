---
title: Ubuntu 20.04 LTS 中安装 PostgreSQL 数据库
description: Ubuntu 20.04 LTS 中安装 PostgreSQL 数据库
published: true
date: 2024-03-06T11:57:31.162Z
tags: ubuntu20, postgresql数据库
editor: markdown
dateCreated: 2024-03-04T05:52:43.693Z
---

Ubuntu 20.04 LTS 中安装 PostgreSQL 数据库的步骤如下：

1. **更新软件源**：打开终端并输入以下命令以更新 Ubuntu 的软件包列表。

    ```bash
    sudo apt update
    ```
2. **安装 PostgreSQL**：使用 `apt` 命令安装 PostgreSQL。

    ```bash
    sudo apt install postgresql
    ```
3. **启动 PostgreSQL 服务**：安装完成后，启动 PostgreSQL 服务并使其在每次启动时自动运行。

    ```bash
    sudo systemctl start postgresql
    sudo systemctl enable postgresql
    ```
4. **设置 PostgreSQL 密码**：为了安全起见，您需要设置 PostgreSQL 的超级用户密码。

    ```bash
    sudo su - postgres
    psql
    ```

    在 `psql>` 命令提示符下输入以下命令来设置密码：

    ```sql
    ALTER USER postgres WITH ENCRYPTED PASSWORD 'your_password';
    ```
5. **退出 PostgreSQL**：完成密码设置后，退出 PostgreSQL。

    ```bash
    \q
    ```
6. **配置防火墙**：如果您的系统启用了 UFW 防火墙，允许 PostgreSQL 服务的通信。

    ```bash
    sudo ufw allow postgresql
    ```
7. **重启 PostgreSQL 服务**：为了使更改生效，重新启动 PostgreSQL 服务。

    ```bash
    sudo systemctl restart postgresql
    ```

完成以上步骤后，您应该已经成功在 Ubuntu 20.04 LTS 上安装并配置了 PostgreSQL 数据库。您可以使用 `psql` 命令行工具或图形界面工具（如 pgAdmin）来管理数据库。