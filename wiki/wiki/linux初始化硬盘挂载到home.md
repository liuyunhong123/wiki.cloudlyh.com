---
title: linux初始化硬盘挂载到/home
description: linux初始化硬盘挂载到/home
published: true
date: 2024-10-20T14:14:12.114Z
tags: linux, 硬盘挂载
editor: markdown
dateCreated: 2024-10-20T14:09:37.863Z
---

# linux初始化硬盘挂载到/home

在 Linux 系统中，将一个新的硬盘挂载到 `/home` 目录下的详细步骤如下：

### 1. **查看新硬盘是否被系统识别**
首先，确保新硬盘已经正确连接到系统。使用以下命令查看系统中的硬盘设备：
```bash
lsblk
```
该命令会显示所有连接的硬盘及其分区信息。假设你看到类似以下的输出：

```
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0   256G  0 disk 
└─sda1   8:1    0   256G  0 part /
sdb      8:16   0   500G  0 disk
```

这里 `sda` 是当前系统的主硬盘，`sdb` 是新添加的硬盘，大小为 500GB。新硬盘通常不会挂载，且没有分区。

### 2. **为新硬盘分区**
如果新硬盘没有分区，使用 `fdisk` 或 `parted` 来进行分区。下面是使用 `fdisk` 进行分区的步骤：

1. 启动 `fdisk`：
   ```bash
   sudo fdisk /dev/sdb
   ```

2. 进入 `fdisk` 交互式命令界面后，输入 `n` 创建新分区，然后按照提示完成操作。最后输入 `w` 保存分区表并退出。你可以选择创建一个主分区。

### 3. **格式化新分区**
创建分区后，假设分区名为 `/dev/sdb1`，你需要格式化该分区。常用的文件系统是 `ext4`。可以通过以下命令格式化分区：
```bash
sudo mkfs.ext4 /dev/sdb1
```

格式化过程完成后，分区已经准备好用于挂载。

### 4. **挂载分区到 `/home`**
接下来，挂载这个分区到 `/home`。你可以先备份现有的 `/home` 目录，尤其是在已经有文件的情况下：
```bash
sudo rsync -av /home/ /path/to/backup/home/
```

然后，挂载新分区：
```bash
sudo mount /dev/sdb1 /home
```

### 5. **更新 `/etc/fstab` 实现自动挂载**
为了在系统重启时自动挂载新硬盘，你需要将其挂载信息写入 `/etc/fstab` 文件。

1. 首先获取分区的 `UUID`（通用唯一标识符），这是用来标识硬盘分区的。运行以下命令来查找分区的 `UUID`：
   ```bash
   sudo blkid /dev/sdb1
   ```

   输出示例：
   ```
   /dev/sdb1: UUID="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" TYPE="ext4"
   ```

2. 记下这个 `UUID`，然后编辑 `/etc/fstab` 文件：
   ```bash
   sudo nano /etc/fstab
   ```

3. 在文件中添加以下行，确保设备自动挂载到 `/home`：
   ```bash
   UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx  /home  ext4  defaults  0  2
   ```

   **解释：**
   - `UUID=xxxxxxxx...`：设备的 `UUID`。
   - `/home`：挂载点。
   - `ext4`：文件系统类型。
   - `defaults`：使用默认挂载选项。
   - `0 2`：文件系统检查选项（`0`表示跳过备份，`2`表示文件系统在启动时检查）。

4. 保存并退出编辑器。

### 6. **测试自动挂载**
运行以下命令，测试 `/etc/fstab` 文件的配置是否正确：
```bash
sudo mount -a
```
如果没有任何错误消息，说明 `fstab` 文件配置正确。

### 7. **检查挂载情况**
可以使用 `df -h` 查看当前挂载的文件系统，确保 `/home` 已正确挂载：
```bash
df -h
```

如果 `/home` 已挂载到 `/dev/sdb1`，你会看到类似的输出：
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1       256G   20G  224G   9% /
/dev/sdb1       500G  1G   499G   1% /home
```

这样，你的 `/home` 目录就成功挂载到新硬盘上了，并且会在每次启动时自动挂载。

### 8. **数据迁移（可选）**
如果你之前备份了 `/home` 中的内容，现在可以将备份的数据复制回新的 `/home` 目录：
```bash
sudo rsync -av /path/to/backup/home/ /home/
```

### 9. **重启系统验证**
最后，你可以重启系统以确保新的硬盘在 `/home` 下能够自动挂载，并正常使用：
```bash
sudo reboot
```

重启后，使用 `df -h` 命令再次检查是否挂载成功。