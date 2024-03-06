---
title: Ubuntu20root账户关闭密码登录开启秘钥登录
description: Ubuntu20root账户关闭密码登录开启秘钥登录
published: true
date: 2024-03-06T11:57:27.464Z
tags: ubuntu20, ssh
editor: markdown
dateCreated: 2024-03-04T05:52:38.543Z
---

在Ubuntu 20.04中，默认情况下，root账户是锁定的，这意味着你不能使用root账户进行登录。这是出于安全考虑的，因为root用户拥有系统上的所有权限，一旦账户被破解，整个系统的安全都会受到威胁。
不过，如果你确实需要开启root账户，并且想要通过SSH密钥进行登录，而不是使用密码，你可以按照以下步骤操作：
1. **启用root账户**:
   如果你还没有启用root账户，首先需要设置一个密码。可以通过以下命令为root用户设置密码：
   ```bash
   sudo passwd root
   ```
   输入这个命令后，系统会提示你输入新的root密码。
2. **生成SSH密钥**:
   如果你还没有SSH密钥，需要生成一个。可以使用`ssh-keygen`命令来生成。打开终端并输入以下命令：
   ```bash
   ssh-keygen -t rsa -b 2048
   ```
   按照提示操作，你可以为密钥设置密码（passphrase），也可以不设置。
3. **将SSH公钥复制到root账户**:
   生成密钥后，需要将公钥复制到root账户的`~/.ssh/authorized_keys`文件中。可以使用`ssh-copy-id`命令：
   ```bash
   sudo ssh-copy-id root@localhost
   ```
   这个命令会提示你输入root的密码，然后就会将你的SSH公钥添加到root账户的授权密钥列表中。
4. **禁用密码登录**:
   为了提高安全性，你可以通过修改SSH服务的配置文件`/etc/ssh/sshd_config`来禁用密码登录。使用文本编辑器打开这个文件：
   ```bash
   sudo nano /etc/ssh/sshd_config
   ```
   找到`PasswordAuthentication`这一行，确保它是这样的：
   ```bash
   PasswordAuthentication no
   ```
   如果这一行被注释掉了，或者设置的是`yes`，你需要做出相应的修改。
5. **重启SSH服务**:
   保存并关闭`sshd_config`文件后，重启SSH服务以应用更改：
   ```bash
   sudo systemctl restart sshd
   ```
完成以上步骤后，你应该可以使用SSH密钥登录root账户，而密码登录将被禁用。请确保你保存了生成的SSH私钥，并且它存储在一个安全的地方，因为这将是你登录root账户的唯一方式。
