---
title: ubuntu20安装PostgreSQL数据库
description: ubuntu20安装PostgreSQL数据库
published: true
date: 2024-04-19T04:34:38.863Z
tags: ubuntu20, postgresql数据库
editor: markdown
dateCreated: 2024-04-19T04:34:38.863Z
---

在Ubuntu 20.04上安装PostgreSQL数据库，你可以遵循以下步骤：
## 1. **更新软件包索引**：
   打开终端并运行以下命令来更新你的软件包索引。
   ```bash
   sudo apt update
   ```
## 2. **安装PostgreSQL**：
   使用下面的命令安装PostgreSQL服务器。
   ```bash
   sudo apt install postgresql postgresql-contrib
   ```
   `postgresql` 软件包包含PostgreSQL服务器，而 `postgresql-contrib` 软件包包含了一些额外的实用程序和功能。
## 3. **初始化数据库**：
   安装完成后，数据库需要被初始化。在早期版本的Ubuntu中，这一步是自动的，但在某些情况下，你可能需要手动执行。
   ```bash
   sudo systemctl start postgresql.service
   sudo systemctl enable postgresql.service
   ```
## 4. **设置PostgreSQL用户密码**：
   默认情况下，PostgreSQL会创建一个名为`postgres`的系统用户，用于管理数据库。要为这个用户设置密码，你需要以`postgres`用户身份登录到PostgreSQL控制台。
   ```bash
   sudo -u postgres psql
   ```
   这将打开一个psql提示符。在psql提示符下，使用以下命令来设置`postgres`用户的密码：
   ```sql
   ALTER USER postgres WITH PASSWORD 'your_password';
   ```
   替换`'your_password'`为你想要设置的密码。
## 5. **配置PostgreSQL以允许远程连接**：
   默认情况下，PostgreSQL只监听本地连接。如果你需要从其他计算机上连接到PostgreSQL服务器，你将需要编辑PostgreSQL的配置文件 `postgresql.conf` 和 `pg_hba.conf`。
   
   首先，打开 `postgresql.conf` 文件：
   ```bash
   sudo nano /etc/postgresql/12/main/postgresql.conf
   ```
   在这个文件中，找到 `listen_addresses` 项，并修改它以允许服务器监听所有接口：
   ```
   listen_addresses = '*'
   ```
   
   接下来，编辑 `pg_hba.conf` 文件来配置客户端认证：
   ```bash
   sudo nano /etc/postgresql/12/main/pg_hba.conf
   ```
   在这个文件中，添加或修改适当的条目以允许来自特定IP地址范围的客户端连接。例如，如果你想允许来自任何IP地址的连接，使用MD5密码认证，你可以添加以下行：
   ```
   host    all             all             0.0.0.0/0               md5
   ```
   
   保存并关闭这两个文件，然后重启PostgreSQL服务：
   ```bash
   sudo systemctl restart postgresql.service
   ```
## 6. **打开防火墙端口**（如果需要的话）：
   如果你的服务器上启用了防火墙，确保打开了PostgreSQL的默认端口（5432）。
   ```bash
   sudo ufw allow 5432/tcp
   ```
完成以上步骤后，你应该能够在Ubuntu 20.04上运行并访问PostgreSQL数据库了。记得，每次对配置文件做出更改后，都需要重新加载或重启PostgreSQL服务。
