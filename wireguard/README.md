***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***


## docker

```

docker run -d \
  --name=wireguard \
  --cap-add=NET_ADMIN \
  --cap-add=SYS_MODULE \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -e SERVERURL=wireguard.domain.com `#optional` \
  -e SERVERPORT=51820 `#optional` \
  -e PEERS=1 `#optional` \
  -e PEERDNS=auto `#optional` \
  -e INTERNAL_SUBNET=10.13.13.0 `#optional` \
  -e ALLOWEDIPS=0.0.0.0/0 `#optional` \
  -p 51820:51820/udp \
  -v /path/to/appdata/config:/config \
  -v /lib/modules:/lib/modules \
  --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
  --restart unless-stopped \
  ghcr.io/linuxserver/wireguard

```