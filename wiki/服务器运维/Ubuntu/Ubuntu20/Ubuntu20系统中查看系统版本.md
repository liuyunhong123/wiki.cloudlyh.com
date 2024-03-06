---
title: Ubuntu20.04系统中查看系统版本
description: Ubuntu20.04系统中查看系统版本
published: true
date: 2024-03-06T11:57:41.205Z
tags: ubuntu20
editor: markdown
dateCreated: 2024-03-04T05:52:57.543Z
---

当然可以。以下是在 Ubuntu 系统中查看系统版本的几种方法的整理：
1. **使用 `lsb_release` 命令**：
   - 打开终端。
   - 输入命令 `lsb_release -a`。
   - 这个命令会显示 LSB 的信息，包括 Ubuntu 的版本号。
2. **查看 `/etc/issue` 文件**：
   - 打开终端。
   - 输入命令 `cat /etc/issue`。
   - 这个命令会显示当前系统的发行版信息，包括版本号。
3. **使用 `hostnamectl` 命令**：
   - 打开终端。
   - 输入命令 `hostnamectl`。
   - 这个命令会显示系统信息，包括操作系统的版本号。
4. **查看 `os-release` 文件**：
   - 打开终端。
   - 输入命令 `cat /etc/os-release`。
   - 这个文件包含了关于操作系统的身份信息，包括版本号。
5. **使用 `uname` 命令**：
   - 打开终端。
   - 输入命令 `uname -a`。
   - 这个命令显示系统内核相关信息，但不会直接显示 Ubuntu 的版本号。
6. **查看 `/etc/lsb-release` 文件**：
   - 打开终端。
   - 输入命令 `cat /etc/lsb-release`。
   - 这个文件也包含了 LSB 相关的信息，包括版本号。
通常，这些命令中的任何一个都会告诉您 Ubuntu 系统的版本号。如果您需要查看特定于 Ubuntu 的版本信息，如 LTS（长期支持）版本或非 LTS 版本，您可能需要结合使用这些命令来获取完整的信息。
