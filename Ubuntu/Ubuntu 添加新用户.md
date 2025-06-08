---
tags:
  - ubuntu
  - ubuntu常用命令
---
## 添加用户
- root 用户下重置root密码：
```bash
passwd root
```

- 添加用户：
```BASH
# root 用户
adduser newuser

# 其他用户
sudo adduser newuser
```

## 为新用户填加超级用户权限
为新用户填加超级用户权限，新用户就能使用**sudo**
```bash
#当前是root权限
visudo
#或
sudo vim /etc/sudoers
#其它用户
sudo visudo
#以前的visudo会用vi打开/etc/sudoers,但新的默认用nano打开
#在文件中添加
#原文件中有类似的root    ALL=(ALL:ALL) ALL
newuser ALL=(ALL:ALL) ALL
```
## 删除用户
```bash
#root用户
deluser newuser
#其它用户
sudo deluser newuser
#删除用户的同时想要删除该用户的home目录
deluser --remove-home newuser
#同理，非root用户
sudo deluser --remove-home newuser
#如果是用第二种方法visudo填加的超级用户权限还需以下命令
visudo #或sudo visudo
```

```
root    ALL=(ALL:ALL) ALL
newuser ALL=(ALL:ALL) ALL   # DELETE THIS LINE
```