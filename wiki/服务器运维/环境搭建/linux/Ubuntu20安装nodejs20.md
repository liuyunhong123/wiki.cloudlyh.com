---
title: Ubuntu20安装nodejs20
description: Ubuntu20安装nodejs20
published: true
date: 2024-04-19T04:29:42.157Z
tags: ubuntu20, node.js
editor: markdown
dateCreated: 2024-04-19T04:29:10.887Z
---

在 Ubuntu 20.04 上安装 Node.js 20 的步骤如下：
## 1. **从 Ubuntu 软件源安装**（不推荐，因为可能不是最新版本）：
   - 打开终端。
   - 更新软件包索引：`sudo apt update`。
   - 安装 Node.js 和 npm：`sudo apt install nodejs npm`。
   - 验证安装：`nodejs --version`。
## 2. **从 NodeSource 源仓库安装**（推荐，可以选择版本）：
   - 打开终端。
   - 更新软件包索引：`sudo apt update`。
   - 安装 curl 和其他必需的包：`sudo apt install -y ca-certificates curl gnupg`。
   - 添加 Node.js 20 的 APT 存储库：
     - 创建目录：`sudo mkdir -p /etc/apt/keyrings`。
     - 导入 GPG 密钥：`curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg`。
     - 添加存储库：`echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list`。
   - 更新软件包索引：`sudo apt update`。
   - 安装 Node.js：`sudo apt install nodejs`。
## 3. **使用 NVM (Node Version Manager) 安装**（适用于需要多个 Node.js 版本的开发者）：
   - 打开终端。
   - 安装 NVM：`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`。
   - 重新加载配置文件：`source ~/.bashrc`。
   - 安装特定版本的 Node.js，例如 20：`nvm install 20`。
   - 切换到该版本：`nvm use 20`。
以上步骤根据阿里云开发者社区、DigitalOcean、ComputingForGeeks 和 Linux-Console 的教程整理而来。安装 Node.js 时，请确保您的操作系统已更新到最新版本，以避免兼容性问题。

## 4.查看node.js版本
```
node -v
```
