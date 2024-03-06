---
title: Centos7修改下载源
description: Centos7修改下载源
published: true
date: 2024-03-06T11:56:42.550Z
tags: centos7
editor: markdown
dateCreated: 2024-03-04T05:51:51.262Z
---

CentOS 7的默认下载源可能在国内访问速度较慢，因此，许多用户选择修改为国内的镜像源以加快软件包的下载速度。以下是修改CentOS 7的yum下载源的一些步骤：
1. **备份当前的yum配置文件**：
   ```bash
   sudo cp -p /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
   ```
2. **选择一个国内的镜像源**，比如阿里云、清华大学、中科大等。以下以阿里云为例。
3. **编辑`CentOS-Base.repo`文件**：
   ```bash
   sudo nano /etc/yum.repos.d/CentOS-Base.repo
   ```
4. **替换文件中的内容**。将文件中的`mirror.centos.org`替换为阿里云的镜像地址，比如`mirrors.aliyun.com`。具体内容大致如下：
   ```ini
   # CentOS-Base.repo
   #
   # The mirror system uses the connecting IP address of the client and the
   # update status of each mirror to pick mirrors that are updated to and
   # geographically close to the client.  You should use this for CentOS updates
   # unless you are manually picking other mirrors.
   
   [base]
   name=CentOS-$releasever - Base
   mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os&infra=$infra
   #baseurl=http://mirror.centos.org/centos/$releasever/os/$basearch/
   baseurl=http://mirrors.aliyun.com/centos/$releasever/os/$basearch/
   gpgcheck=1
   gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
   
   #released updates
   [updates]
   name=CentOS-$releasever - Updates
   mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=updates&infra=$infra
   #baseurl=http://mirror.centos.org/centos/$releasever/updates/$basearch/
   baseurl=http://mirrors.aliyun.com/centos/$releasever/updates/$basearch/
   gpgcheck=1
   gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
   
   #additional packages that may be useful
   [extras]
   name=CentOS-$releasever - Extras
   mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=extras&infra=$infra
   #baseurl=http://mirror.centos.org/centos/$releasever/extras/$basearch/
   baseurl=http://mirrors.aliyun.com/centos/$releasever/extras/$basearch/
   gpgcheck=1
   gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
   
   #additional packages that extend functionality of existing packages
   [centosplus]
   name=CentOS-$releasever - Plus
   mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=centosplus&infra=$infra
   #baseurl=http://mirror.centos.org/centos/$releasever/centosplus/$basearch/
   baseurl=http://mirrors.aliyun.com/centos/$releasever/centosplus/$basearch/
   gpgcheck=1
   enabled=0
   gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
   
   #contrib - packages by Centos Users
   [contrib]
   name=CentOS-$releasever - Contrib
   mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=contrib&infra=$infra
   #baseurl=http://mirror.centos.org/centos/$releasever/contrib/$basearch/
   baseurl=http://mirrors.aliyun.com/centos/$releasever/contrib/$basearch/
   gpgcheck=1
   enabled=0
   gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
   ```
5. **保存并退出编辑器**。如果使用的是`nano`，可以按`Ctrl + O`保存文件，然后按`Ctrl + X`退出。
6. **清理yum缓存并更新yum**：
   ```bash
   sudo yum clean all
   sudo yum makecache
   ```
7. **更新系统**：
   ```bash
   sudo yum update
   ```
完成上述步骤后，CentOS 7的yum
