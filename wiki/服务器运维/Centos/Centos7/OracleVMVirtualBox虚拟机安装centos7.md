---
title: OracleVMVirtualBox虚拟机安装centos7.9
description: OracleVMVirtualBox虚拟机安装centos7.9
published: true
date: 2024-03-22T12:08:51.846Z
tags: centos7
editor: markdown
dateCreated: 2024-03-12T03:11:54.377Z
---

## 1. 打开虚拟机软件
![vmbox虚拟机开始界面.png](/wiki/服务器运维/Centos/vmbox虚拟机开始界面.png)
## 2. 点击新建
![vmbox新建虚拟机.png](/wiki/服务器运维/Centos/vmbox新建虚拟机.png)
## 3. 新建虚拟机名称与操作系统
![vmbox新建虚拟机名称与操作系统.png](/wiki/服务器运维/Centos/vmbox新建虚拟机名称与操作系统.png)
## 4. 新建虚拟机硬件配置
![vmbox新建虚拟机硬件配置.png](/wiki/服务器运维/Centos/vmbox新建虚拟机硬件配置.png)
## 5. 新建虚拟硬盘
![vmbox新建虚拟硬盘.png](/wiki/服务器运维/Centos/vmbox新建虚拟硬盘.png)
## 6. 检查配置后点击完成
![vmbox虚拟机配置.png](/wiki/服务器运维/Centos/vmbox虚拟机配置.png)
## 7. 启动centos7.9虚拟机设置
![启动centos7.9虚拟机设置.png](/wiki/服务器运维/Centos/启动centos7.9虚拟机设置.png)
## 8. 设置启动引导
![vmbox设置启动引导.png](/wiki/服务器运维/Centos/vmbox设置启动引导.png)
## 9. 选择需要启动的虚拟机，然后点击启动
![vmbox虚拟机安装centos7版本01.png](/wiki/服务器运维/Centos/vmbox虚拟机安装centos7版本01.png)
## 10. 跑完加载后选择第一个Install Centos7安装系统
![vmbox虚拟机安装centos7版本02.png](/wiki/服务器运维/Centos/vmbox虚拟机安装centos7版本02.png)
## 11. 开始配置安装选项
### 1. 选择安装语言=>中文=>简体中文=>继续
![vmbox虚拟机安装centos7版本03.png](/wiki/服务器运维/Centos/vmbox虚拟机安装centos7版本03.png)
### 2. 选择系统安装到哪一块硬盘（磁盘分区）
![vmbox虚拟机安装centos7版本04.png](/wiki/服务器运维/Centos/vmbox虚拟机安装centos7版本04.png)
### 3. 勾选磁盘=>我要配置分区=>点击完成
![vmbox虚拟机安装centos7版本05.png](/wiki/服务器运维/Centos/vmbox虚拟机安装centos7版本05.png)
### 4. 自动分区=>点这里自动创建他们
![手动分区之自动分区.png](/wiki/服务器运维/Centos/手动分区之自动分区.png)
### 5. 设备类型建议LVM，文件系统建议XFS，因为这样后期可以扩容或者修复损坏文件
![分区含义.png](/wiki/服务器运维/Centos/分区含义.png)
### 6. 分区介绍
![分区介绍.png](/wiki/服务器运维/Centos/分区介绍.png)
### 7. 检查分区后点击接受更改
![检查分区点击完成.png](/wiki/服务器运维/Centos/检查分区点击完成.png)
### 8. 配置IP和子网掩码
![配置ip.png](/wiki/服务器运维/Centos/配置ip.png)
### 9. 打开网络链接开关
![打开网络链接开关.png](/wiki/服务器运维/Centos/打开网络链接开关.png)
### 10. windows10打开命令提示符
![win10打开命令提示符.png](/wiki/服务器运维/Centos/win10打开命令提示符.png)
### 11. win10查看本地ip
![win10查看本地ip.png](/wiki/服务器运维/Centos/win10查看本地ip.png)
### 12. 使用win10的CMD测试可以使用的静态IP
![可取的ip及范围.png](/wiki/服务器运维/Centos/可取的ip及范围.png)
### 13. 配置静态IP
![配置静态ip.png](/wiki/服务器运维/Centos/配置静态ip.png)
### 14. 设置静态ip地址子网掩码网关和dns
![设置静态ip地址子网掩码网关和dns.png](/wiki/服务器运维/Centos/设置静态ip地址子网掩码网关和dns.png)
### 15. 静态ip配置完成
![静态ip配置完成.png](/wiki/服务器运维/Centos/静态ip配置完成.png)
### 16. 可选软件安装(比如安装桌面、虚拟化等)
![可选软件安装().png](/wiki/服务器运维/Centos/可选软件安装.png)
### 17. kdump内存崩溃转储机制
![kdump内存崩溃转储机制01.png](/wiki/服务器运维/Centos/kdump内存崩溃转储机制01.png)
![kdump内存崩溃转储机制.png](/wiki/服务器运维/Centos/kdump内存崩溃转储机制.png)
### 18. 点击开始安装系统
![开始安装系统.png](/wiki/服务器运维/Centos/开始安装系统.png)
### 19. 设置密码和创建一个用户
![设置密码和创建一个用户.png](/wiki/服务器运维/Centos/设置密码和创建一个用户.png)
### 20. 设置密码(密码太弱需要点击两次确认)
我这里是演示，密码设置的：123456，不建议密码设置太弱，可能会被入侵
![设置密码.png](/wiki/服务器运维/Centos/设置密码.png)
### 21. 创建用户
我这里设置的是一个普通账户，没有勾选作为管理员
无论是密码还是账户还有权限都是可以修改的
![设置一个普通用户.png](/wiki/服务器运维/Centos/设置一个普通用户.png)
### 22. 系统安装完成，点击完成配置即可
![系统安装完成.png](/wiki/服务器运维/Centos/系统安装完成.png)
### 23. 系统安装完成点击重启
![系统安装完成点击重启.png](/wiki/服务器运维/Centos/系统安装完成点击重启.png)
### 24. 已经重启到登录界面
![已经重启到登录界面.png](/wiki/服务器运维/Centos/已经重启到登录界面.png)
### 25. 第一次登录发现没有网络
![第一次登录发现没有网络.png](/wiki/服务器运维/Centos/第一次登录发现没有网络.png)
### 26. 

