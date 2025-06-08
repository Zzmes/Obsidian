---
tags:
  - SSH
  - ubuntu
  - ubuntu常用命令
日期: 2025-06-08
---
##  安装 openssh-server
```bash
sudo apt-get update
sudo apt-get install openssh-server
```

## 配置 ssh
允许root用户登陆：
```BASH
sudo vim /etc/ssh/sshd_config

# 对应配置文件：
PermitRootLogin yes
```

## 重启 SSH 服务
```bash
systemctl restart sshd.service
```

## 其他
- 启动SSH服务：
```bash
sudo service ssh start
# 或者
sudo systemctl ssh start
```
- 设置开机自启动：
```bash
   sudo systemctl enable ssh
```
- 检查 SSH 服务状态
```BASH
sudo service ssh status
# 或者
sudo systemctl status ssh
```

- SSH连接:
```bash
ssh your_username@your_server_ip
```