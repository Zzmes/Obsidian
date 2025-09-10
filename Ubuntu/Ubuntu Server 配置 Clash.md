## 安装 clash
- 启动
```bash
cd /opt/clash
./clash -d ~/.config/clash .
```
- 设置系统代理
```bash
sudo nano /etc/environment
// 加入以下三行
export http_proxy="http://127.0.0.1:7890"
export https_proxy="http://127.0.0.1:7890"
export no_proxy="localhost,127.0.0.1"
```
- 修改sudo文件，然后重启
```bash
// 后面加上
Defaults env_keep+="http_proxy https_proxy no_proxy"
```
- 不想重启也可以使用，下列命令刷新一下
```bash
source /etc/environment
#禁用全局代理
unset http_proxy
unset https_proxy
#启用全局代理
set http_proxy
set https_proxy
```
## 设置clash开机启动
- 创建服务文件：
```bash
sudo nano /etc/systemd/system/clash.service
```
- 填入以下内容（修改路径为你的 Clash 可执行文件和配置文件路径）：
```text
[Unit]
Description=Clash Service
After=network.target

[Service]
Type=simple
ExecStart=/home/zzmes/workspace/tools/clash/clash -d /home/zzmes/workspace/tools/clash
Restart=on-failure
User=zzmes
WorkingDirectory=/home/zzmes/workspace/tools/clash

[Install]
WantedBy=multi-user.target
```
- 保存后执行：
```bash
sudo systemctl daemon-reload
sudo systemctl enable clash      # 开机启动
sudo systemctl start clash       # 立即启动
sudo systemctl status clash      # 查看状态
```
## Clash相关的管理命令
```bash
#启动Clash
sudo systemctl start clash.service
#重启Clash
sudo systemctl restart clash.service
#查看Clash运行状态
sudo systemctl status clash.service
#禁用全局代理
unset http_proxy
unset https_proxy
#启用全局代理
set http_proxy
set https_proxy
```

