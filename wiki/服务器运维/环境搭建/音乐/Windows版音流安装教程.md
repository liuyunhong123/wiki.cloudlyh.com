---
title: Windows版音流安装教程
description: Windows版音流安装教程
published: true
date: 2024-03-06T11:57:50.522Z
tags: 音流
editor: markdown
dateCreated: 2024-03-04T05:53:12.535Z
---

# Windows 版音流安装教程
Windows 版音流目前只提供 x64 架构的 msix 格式安装包，这是微软应用商店的安装格式，因此在商店外安装，需要先在电脑上安装开发者对应的证书。
> 音流对应的证书：[stream_music_win.crt](/音流/stream_music_win.crt)下载地址
{.is-info}


一、标准安装方式
双击证书文件开始安装，安装位置选择`本地计算机`。
![音流导入证书.png](/wiki/音流/音流导入证书.png)
下一步，将证书存储到`受信任的根证书颁发机构`中。
![音流证书安装路径.png](/wiki/音流/音流证书安装路径.png)
安装完成后，以后就可以直接双击`msix`格式的安装包进行安装了。

二、非标准安装方式
msix 格式对系统的要求较高，需要 win10 以上才可使用，对于还停留在 win7 或 win8 的用户，可通过此种方式安装。
> 经用户反馈，win7 安装时会报错缺少 xxx.dll，而且不止一个。。。
{.is-warning}

首先下载音流 msix 格式的安装包，使用任意压缩软件打开：
![使用压缩软件打开音流安装包.png](/wiki/音流/使用压缩软件打开音流安装包.png)
把压缩包内的文件全部解压到你想要安装的位置，然后通过`stream_music.exe`打开软件即可。
![选择音流安装包.png](/wiki/音流/选择音流安装包.png)

 版权归属：贯耳症
 本文转载链接： https://aqzscn.cn/archives/stream-music-win
 许可协议： 本文使用《署名-非商业性使用-相同方式共享 4.0 国际 (CC BY-NC-SA 4.0)》协议授权

