---
title: ubuntu20.04设置自动同步时间
description: ubuntu20.04设置自动同步时间
published: true
date: 2024-09-27T13:20:51.270Z
tags: ubuntu20
editor: markdown
dateCreated: 2024-09-27T12:18:42.951Z
---

# ubuntu20.04
## 1.首先使用命令date发现时间不对
```
date
```
![01.date时间不正确.png](/wiki/wiki/ubuntu20设置自动同步时间/01.date时间不正确.png)

## 2.查看当前时区
```
timedatectl
```
![02.查看当前时区.png](/wiki/wiki/ubuntu20设置自动同步时间/02.查看当前时区.png)

## 3.设置时区为北京上海
```
timedatectl set-timezone Asia/Shanghai
```
![03.设置时区为北京上海.png](/wiki/wiki/ubuntu20设置自动同步时间/03.设置时区为北京上海.png)

## 4.使用以下命令查看 chrony 的同步状态：
```
chronyc sources
```
![04.查看当前同步时间.png](/wiki/wiki/ubuntu20设置自动同步时间/04.查看当前同步时间.png)
chronyc sources 输出显示所有 NTP 服务器都没有回应 (Reach = 0)，这意味着系统没有成功连接到时间服务器。尝试以下步骤来解决这个问题。

## 5.手动更新时间同步源
你可以尝试更改或添加一些可用的 NTP 服务器。编辑 /etc/chrony.conf 文件，添加一些可靠的中国 NTP 服务器，如：
```
vi /etc/chrony.conf
```
在文件中找到类似以下行：
```
server 0.centos.pool.ntp.org iburst
server 1.centos.pool.ntp.org iburst
server 2.centos.pool.ntp.org iburst
server 3.centos.pool.ntp.org iburst
```
将它们替换为以下 NTP 服务器（或添加新行）：

```
server ntp.aliyun.com iburst
server ntp1.aliyun.com iburst
server ntp2.aliyun.com iburst
server cn.pool.ntp.org iburst
server dns1.synet.edu.cn iburst
```
## 6.重新启动 chronyd 服务
编辑完后，重新启动 chronyd 服务：
```
systemctl restart chronyd
```
## 7.检查 chronyc 的时间源状态
重新运行以下命令检查时间源是否正常：
```
chronyc sources
```
如果一切正常，你应该看到 Reach 值从 0 变为其他值（比如 377），这意味着 NTP 同步正在工作。

如果 chronyc sources 中 Reach 值依然为 0，意味着 chronyd 仍然无法连接到 NTP 服务器。可以尝试以下排查步骤：
## 8.检查网络连接
确保服务器能够访问外部网络，特别是 NTP 服务器。你可以通过以下命令测试是否能连通 NTP 服务器：
```
ping ntp.aliyun.com
```
## 9.如果无法 ping 通，可能是防火墙或网络配置阻止了 NTP 流量。






