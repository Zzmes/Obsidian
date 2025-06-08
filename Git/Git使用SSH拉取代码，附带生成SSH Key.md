---
tags:
  - Git
  - 生成Key
  - 管理本地项目
---
## 查看电脑上是否已经存在SSH 公钥

```bash
cd ~/.ssh 
ls
```
默认情况下，用户的SSH密钥存储在.ssh目录下，如果有id_rsa、id_rsa.pub这两个文件说明你已经生成过SSH密钥了，请跳过以下生成步骤。其中id_rsa是私钥，而id_rsa.pub是公钥。

## 生成SSH密钥
```bash
ssh-keygen -t rsa -C "这里换上你的邮箱"
```
回车后：
- 首先会让你确认密钥的生成位置，如果不需要更改路径则直接回车（建议不更改）。如果这个路径下已经存在密钥则需要让你确认是否需要覆盖旧密钥文件
- 之后会让你输入密码，如果不需要则直接回车
- 会让你再次确认密码，保持和上一步一致，如果上一步没输入则直接回车
这时就会告诉你已经生成成功了

## 配置SSH密钥
```bash
cd ~/.ssh
cat id_rsa.pub
```
将公钥全部复制到你的github中(Settings->SSH and GPG keys -> New SSH key)
至此就配置成功了。