# 使用 Docker Cli 安装面板

## 需要安装 Docker

```bash
sudo su
curl -sSL https://get.daocloud.io/docker | sh
apt update && apt install docker-compose
```
## 只需执行以下命令即可部署


## Web

```bash
docker run --name mcsmv9_web \
--network host \
-v /opt/docker-mcsm/web:/opt/web/data \
-v /opt/docker-mcsm/web/logs:/opt/web/logs \
-v /opt/docker-mcsm/daemon/data/Config:/opt/daemon/data/Config:ro \
registry.cn-guangzhou.aliyuncs.com/kabaka/kabaka:mcsmv9_web
```

## Daemon

```bash
docker run --name mcsmv9_daemon \
--network host \
-v /opt/docker-mcsm/daemon/data:/opt/daemon/data \
-v /opt/docker-mcsm/daemon/logs:/opt/daemon/logs \
-v /opt/docker-mcsm/daemon/lib:/opt/daemon/lib \
-v /var/run/docker.sock:/var/run/docker.sock:ro \
registry.cn-guangzhou.aliyuncs.com/kabaka/kabaka:mcsmv9_daemon
```

- 数据存放位置位于 `/opt/docker-mcsm`
