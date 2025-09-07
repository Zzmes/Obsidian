---
日期: 2025-09-06
tags:
  - ubuntu
  - 交换空间
---
```bash
sudo systemctl disable nvzramconfig
sudo fallocate -l 16G /mnt/16GB.swap
sudo mkswap /mnt/16GB.swap
sudo swapon /mnt/16GB.swap
```

然后在`/etc/fstab`的末尾添加以下行，以使更改永久生效：
```bash
/mnt/16GB.swap  none  swap  sw 0  0
```

取消:
```bash
sudo swapoff /mnt/16GB.swap
sudo rm /mnt/16GB.swap
sudo systemctl enable nvzramconfig
sudo systemctl start nvzramconfig
```
删除 fstab 中的挂载记录
```bash
/mnt/16GB.swap  none  swap  sw 0  0
```

## 禁用桌面图形用户界面
可以临时禁用桌面，在控制台中运行命令，然后在需要时重新启动桌面：
```bash
sudo init 3     # 停止桌面
// 使用Ctrl+Alt+F1、F2等组合键让用户重新登录到控制台
sudo init 5     # 重新启动桌面
```

如果希望在重启后该设置仍然生效，可以使用以下命令来更改启动行为：
```bash
sudo systemctl set-default multi-user.target     # 启动时禁用桌面
sudo systemctl set-default graphical.target      # 启动时启用桌面
```
