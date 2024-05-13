---
title: pip配置清华源下载
description: pip配置清华源下载
published: true
date: 2024-05-13T17:11:38.263Z
tags: pip
editor: markdown
dateCreated: 2024-05-13T17:11:38.263Z
---

# pip配置清华源下载
要修改 `pip` 的配置文件，您需要找到或创建 `pip` 的配置文件。这个配置文件通常位于以下几个位置之一：
- 对于Unix和macOS系统，配置文件通常位于 `~/.pip/pip.conf`。
- 对于Windows系统，配置文件通常位于 `C:\Users\<Username>\pip\pip.ini`。
如果文件不存在，您可以创建一个新的配置文件。以下是如何在各个操作系统中修改或创建 `pip` 配置文件的步骤：
### 对于Unix和macOS：
1. 打开终端。
2. 使用文本编辑器创建或编辑 `~/.pip/pip.conf` 文件。例如，使用 `nano` 编辑器：
```bash
nano ~/.pip/pip.conf
```
3. 如果文件不存在，您将看到一个空白文件。添加以下内容来使用清华大学的镜像源：
```ini
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```
4. 保存并关闭文件（在 `nano` 中，按 `Ctrl + X`，然后按 `Y` 确认保存，最后按 `Enter` 键）。
### 对于Windows：
1. 打开文件资源管理器。
2. 导航到 `C:\Users\<Username>\pip\` 目录。如果 `pip` 目录不存在，您需要创建它。
3. 在 `pip` 目录中，创建或编辑一个名为 `pip.ini` 的文件。
4. 使用文本编辑器打开 `pip.ini` 文件，并添加以下内容：
```ini
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```
5. 保存并关闭文件。
### 对于所有系统：
您还可以设置环境变量 `PIP_CONFIG_FILE` 来指定 `pip` 配置文件的位置。这样，您可以将配置文件放在任何您喜欢的地方，并告诉 `pip` 去那里查找它。
完成这些步骤后，`pip` 将使用您指定的镜像源来下载和安装 Python 包。

## 例子：
下载django5的Pillow库（用于models.ImageField）
```
pip install --find-links=https://github.com/python-pillow/Pillow/releases Pillow
```
