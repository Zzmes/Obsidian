---
tags:
  - zsh
  - ubuntu
  - 终端美化
日期: 2025-06-08
---
## 环境配置
- 安装基本工具：
```bash
# 更新软件源
sudo apt update && sudo apt upgrade -y
# 安装 zsh git curl
sudo apt install zsh git curl -y
```
- 设置默认终端为 zsh（**注意：不要使用 sudo**）
```bash
chsh -s /bin/zsh
```
- 安装 oh-my-zsh（以下任选一个就可以）:

| Method  | Command                                                                            |
| ------- | ---------------------------------------------------------------------------------- |
| curl    | sh -c "$(curl -fsSL https://install.ohmyz.sh/)"                                    |
| wget    | sh -c "$(wget -O- https://install.ohmyz.sh/)"                                      |
| fetch   | sh -c "$(fetch -o - https://install.ohmyz.sh/)"                                    |
| 国内curl源 | sh -c "$(curl -fsSL https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)" |
| 国内wget源 | sh -c "$(wget -O- https://gitee.com/pocmon/ohmyzsh/raw/master/tools/install.sh)"   |


[[Ubuntu/_resources/ubutnu 终端zsh美化/61f36fc8cf9267177487f0865dad4625_MD5.jpeg|Open: Pasted image 20250608182713.png]]
![[Ubuntu/_resources/ubutnu 终端zsh美化/61f36fc8cf9267177487f0865dad4625_MD5.jpeg]]
这样on-my-zsh就安装成功了。

## 配置主题和插件
- 主题
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

# 中国用户可以使用 gitee.com 上的官方镜像加速下载
git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
- zsh -autosuggestions插件：
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# 中国用户可以使用下面任意一个加速下载
# 加速1
git clone https://github.moeyy.xyz/https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# 加速2
git clone https://gh.xmly.dev/https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# 加速3
git clone https://gh.api.99988866.xyz/https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
-  zsh-syntax-highlighting插件：
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# 中国用户可以使用下面任意一个加速下载
# 加速1
git clone https://github.moeyy.xyz/https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# 加速2
git clone https://gh.xmly.dev/https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# 加速3
git clone https://gh.api.99988866.xyz/https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

## 修改~/.zshrc 启用主题和插件
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
plugins=(git zsh-autosuggestions zsh-syntax-highlighting z extract web-search)
```

## 其他
- powerlevel10k主题重新配置
```bash
p10k configure
```