---
日期: 2025-09-06
tags:
---

- git下载
```bash
git clone https://github.com/pytorch/pytorch --recursive && cd pytorch
	git checkout v2.8.0 # 切换分支
#下载编译需要的子模块
	git submodule sync
git submodule update --init --recursive
```
- 源码编译
```python
python ../tools/build_libtorch.py
```