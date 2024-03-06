---
title: Debian12更换阿里源
description: Debian12更换阿里源
published: true
date: 2024-03-06T11:57:07.842Z
tags: debian12
editor: markdown
dateCreated: 2024-03-04T05:52:14.298Z
---

1. 直接编辑 `/etc/apt/sources.list` 文件

```
vim.tiny /etc/apt/sources.list
```

更改为这个

```
deb https://mirrors.aliyun.com/debian/ bookworm main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm main non-free non-free-firmware contrib
deb https://mirrors.aliyun.com/debian-security/ bookworm-security main
deb-src https://mirrors.aliyun.com/debian-security/ bookworm-security main
deb https://mirrors.aliyun.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm-updates main non-free non-free-firmware contrib
deb https://mirrors.aliyun.com/debian/ bookworm-backports main non-free non-free-firmware contrib
deb-src https://mirrors.aliyun.com/debian/ bookworm-backports main non-free non-free-firmware contrib
```

2. 然后执行更新软件源

```
apt update
```

3. 执行更新系统(可省略)

```
apt upgraade
```