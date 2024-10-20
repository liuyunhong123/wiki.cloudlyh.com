---
title: 怎么查看linux是什么系统分支
description: 怎么查看linux是什么系统分支
published: true
date: 2024-10-20T14:13:29.866Z
tags: linux
editor: markdown
dateCreated: 2024-10-20T14:12:25.427Z
---

# 怎么查看linux是什么系统分支
在 Linux 系统中，你可以通过以下几种方式来查看系统的发行版本和分支：

### 1. **`/etc/os-release` 文件**
这个文件包含了大部分 Linux 发行版的信息，你可以通过以下命令查看：
```bash
cat /etc/os-release
```
输出内容中会包括系统名称、版本等信息。例如：
```bash
NAME="Ubuntu"
VERSION="20.04.6 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
```

### 2. **`lsb_release` 命令**
如果你的系统支持 `lsb_release` 命令，你可以使用这个命令来查看系统版本信息：
```bash
lsb_release -a
```
输出示例：
```bash
Distributor ID: Ubuntu
Description:    Ubuntu 20.04.6 LTS
Release:        20.04
Codename:       focal
```

### 3. **`hostnamectl` 命令**
这个命令不仅可以查看主机名，还可以查看操作系统信息：
```bash
hostnamectl
```
输出示例：
```bash
Operating System: Ubuntu 20.04.6 LTS
Kernel: Linux 5.4.0-144-generic
Architecture: x86-64
```

### 4. **`uname` 命令**
`uname` 命令可以显示系统内核信息，不过它不会告诉你具体的发行版，但对于排查系统架构还是有帮助的：
```bash
uname -a
```
输出示例：
```bash
Linux yourhostname 5.4.0-144-generic #160-Ubuntu SMP x86_64 GNU/Linux

```

通过这些命令，你可以轻松获取到你正在使用的 Linux 系统的分支信息。