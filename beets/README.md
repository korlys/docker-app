***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***

### docker


```

docker run -d \
  --name=beets \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -p 8337:8337 \
  -v </path/to/appdata/config>:/config \
  -v </path/to/music/library>:/music \
  -v </path/to/ingest>:/downloads \
  --restart unless-stopped \
  ghcr.io/linuxserver/beets

```