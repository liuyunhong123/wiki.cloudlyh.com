---
title: linux的smb禁止匿名用户访问
description: linux的smb禁止匿名用户访问
published: true
date: 2024-08-25T16:28:22.732Z
tags: smb, linux
editor: markdown
dateCreated: 2024-08-25T16:28:22.732Z
---

# linux的smb禁止匿名用户访问
在Linux系统中，使用Samba服务来实现SMB共享。要禁止匿名用户访问SMB共享，你需要编辑Samba的配置文件，通常是`/etc/samba/smb.conf`。以下是具体步骤：
1. **打开Samba配置文件**：
   使用文本编辑器打开Samba配置文件。例如，使用`nano`编辑器：
   ```bash
   sudo nano /etc/samba/smb.conf
   ```
2. **找到[global]部分**：
   在配置文件中找到 `[global]` 部分。
3. **设置匿名访问**：
   在 `[global]` 部分中，确保以下选项设置如下：
   ```
   map to guest = never
   guest ok = no
   ```
   - `map to guest = never` 确保不会将任何用户映射到guest账户。
   - `guest ok = no` 确保不允许匿名访问。
4. **保存并关闭文件**：
   在`nano`编辑器中，按`Ctrl + O`保存文件，然后按`Ctrl + X`退出。
5. **重启Samba服务**：
   应用配置更改，需要重启Samba服务：
   ```bash
   sudo systemctl restart smbd
   ```
或者，如果你使用的是旧版的Samba或系统，可能需要使用以下命令来重启服务：
```bash
sudo service smbd restart
```
或者：
```bash
sudo /etc/init.d/smbd restart
```
确保你的Samba共享的配置也反映了不允许匿名访问。在每个共享部分（例如 `[sharename]`），也应该设置 `guest ok = no`。
以上步骤完成后，你的SMB服务器应该不再允许匿名用户访问。只有通过验证的用户才能访问SMB共享。请确保测试配置更改，以确保它们按预期工作，并且不会影响授权用户的访问。
