---
tags:
  - Git
  - 管理本地项目
---
## git初始化
- 本地项目执行：
```bash
git init
```
- 使用新分支名称
```bash
git config --global init.defaultBranch main
```
如果已经创建了仓库，并且希望将 *master*分支重命名为 *main*，你可以执行以下命令：
```bash
git branch -m main
```
## 本地与远程仓库关联（前提新建远程仓库）
- 关联远程仓库：
```bash
git remote add origin git@github.com:Zzmes/dotfiles.git
```

## 上传代码
- 更新主分支：
```bash
git fetch
```
- 变基：
```bash
git rebase orign main
```
- 上传代码：
```bash
git push origin main
```

## 其他
- 查看当前的远程仓库地址
```bash
git remote -v
```
- 更改远程仓库地址
```bash
git remote set-url origin git@github.com:Zzmes/dotfiles.git
```