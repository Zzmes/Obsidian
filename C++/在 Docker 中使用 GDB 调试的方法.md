---
tags:
  - 调试技巧
  - GDB
  - docker创建容器
日期: 2025-06-08
---
## 创建 docker 容器
启动 docker 容器命令*run*时，需要添加`--privileged`, `--cap-add=SYS_PTRACE`, `--security-opt seccomp=unconfined`参数，例如：
```bash
docker run --privileged -d -it  --cap-add=SYS_PTRACE --security-opt seccomp=unconfined [your_container_id]
```

创建容器案例：
```bash
docker run --privileged -itd -p 10001:22 --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --gpus all --shm-size=8G -v /home/zzmes/code:/home/code -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY -e GDK_SCALE -e GDK_DPI_SCALE --name cuda128 468c101db63b /bin/bash
```

如果不需要实现端口映射：
```bash
docker run --privileged -itd --ipc=host --net=host --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --gpus all --shm-size=8G -v /home/zzmes/code:/home/code -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY -e GDK_SCALE -e GDK_DPI_SCALE --name cuda128 468c101db63b /bin/bash
```
