---
title: Ubuntu20搭建SMB服务
description: Ubuntu20搭建SMB服务
published: true
date: 2024-04-18T15:41:27.753Z
tags: ubuntu20, smb
editor: markdown
dateCreated: 2024-04-18T15:22:53.161Z
---

在Ubuntu 20.04上搭建SMB（Server Message Block）服务器，可以让您轻松地在局域网内共享文件和打印机。以下是在Ubuntu 20.04上搭建SMB服务器的步骤：
## 1. **安装SMB服务器（Samba）**：
   打开终端，使用以下命令安装Samba包：
   ```bash
   sudo apt update
   sudo apt install samba
   ```
## 2. **创建共享目录**：
   决定哪个目录将被共享，然后创建它。例如，创建一个名为`shared`的目录：
   ```bash
   sudo mkdir /path/to/shared
   ```
   替换`/path/to/`为您的实际路径。
## 3. **设置目录权限**：
   为了让Samba能够访问这个目录，您需要确保Samba服务有足够的权限。通常，会将所有权更改为`nobody:nogroup`，并设置相应的权限：
   ```bash
   sudo chown nobody:nogroup /path/to/shared
   sudo chmod 777 /path/to/shared
   ```
   注意：在生产环境中，这样的权限设置可能过于宽松，建议根据实际情况调整。
## 4. **配置Samba**：
   编辑Samba的配置文件`/etc/samba/smb.conf`：
   ```bash
   sudo nano /etc/samba/smb.conf
   ```
   在文件的最后添加以下配置：
   ```ini
   [shared]
   comment = Shared Folder
   path = /path/to/shared
   browseable = yes
   read only = no
   guest ok = yes
   create mask = 0777
   directory mask = 0777
   ```
   根据需要替换`[shared]`、`comment`和`path`的值。
## 5. **重启Samba服务**：
   应用更改后，需要重启Samba服务：
   ```bash
   sudo systemctl restart smbd
   ```
## 6. **防火墙设置**：
   如果您的系统启用了ufw防火墙，您需要允许SMB服务通过：
   ```bash
   sudo ufw allow 'Samba'
   ```
## 7. **测试SMB共享**：
   在另一台Windows或Linux计算机上尝试访问您刚创建的共享目录，看看是否可以成功连接。
## 8. **添加Samba用户**（可选）：
   如果您希望用户使用用户名和密码访问共享，而不是作为来宾访问，您需要添加Samba用户：
   ```bash
   sudo smbpasswd -a username
   ```
   替换`username`为实际的用户名，并按照提示设置密码。
以上步骤应该可以帮助您在Ubuntu 20.04上搭建一个基本的SMB服务器。请根据您的具体需求调整权限和配置。在生产环境中，为了安全起见，请遵循最佳实践进行配置，例如限制目录权限，创建专用的Samba用户等。

## 9.win10提示已经有映射的文件目录
以管理员身份映射： 如果您是管理员，可以尝试以管理员身份映射网络驱动器。右键点击“此电脑”，选择“映射网络驱动器”，然后选择一个未被使用的驱动器字母。在“文件夹”栏中输入网络路径，并选择“使用其他凭据”。输入管理员账户的凭据，然后点击“确定”。

断开现有映射： 如果您有管理员权限，可以断开其他用户映射的网络驱动器。以管理员身份打开命令提示符，使用以下命令：
```
net use 驱动器字母: /delete
```
清理所有映射的网络驱动器： 如果您想要清理所有用户映射的网络驱动器，可以使用以下命令：
```
这个命令会断开所有映射的网络驱动器。请注意，这可能会影响其他用户的正常工作，因此请谨慎操作。
```

