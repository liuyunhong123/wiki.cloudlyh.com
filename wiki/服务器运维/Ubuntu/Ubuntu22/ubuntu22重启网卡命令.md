---
title: ubuntu22.04重启网卡命令
description: ubuntu22.04重启网卡命令
published: true
date: 2024-10-19T14:45:05.767Z
tags: ubuntu22
editor: markdown
dateCreated: 2024-10-19T14:45:05.767Z
---

# ubuntu22.04重启网卡命令
在 Ubuntu 22.04 中，你可以使用以下命令来重启网卡：

### 1. **使用 `netplan` 重启网络**
Ubuntu 22.04 使用 `netplan` 来管理网络配置。你可以通过以下命令重启网络：
```bash
sudo netplan apply
```

### 2. **使用 `systemctl` 重启 `NetworkManager`**
Ubuntu 22.04 默认使用 `NetworkManager` 来管理网络服务，你可以通过 `systemctl` 来重启网络服务：
```bash
sudo systemctl restart NetworkManager
```

### 3. **重启指定的网络接口**
如果你只想重启某个特定的网络接口（例如 `eth0` 或 `wlan0`），可以使用 `ip` 命令：
```bash
sudo ip link set eth0 down
sudo ip link set eth0 up
```

将 `eth0` 替换为你想重启的网卡名称。

### 4. **使用 `nmcli` 重启网络接口**
你也可以通过 `nmcli` 命令来重启特定的网络接口：
```bash
sudo nmcli networking off
sudo nmcli networking on
```

### 5. **使用 `ifdown` 和 `ifup` 重启网络接口**
你还可以使用 `ifdown` 和 `ifup` 命令来关闭和开启网络接口：
```bash
sudo ifdown eth0 && sudo ifup eth0
```

通过这些命令，你可以根据实际需求来选择不同的方式重启网络服务或接口。