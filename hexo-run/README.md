***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***



### config  配置

create  new file `docker-compose.yml ` `run.sh` and a folder `hexo`

创建新文件 `docker-compose.yml ` `run.sh` 和一个目录`hexo`

copy hexo source file to `hexo`folder

复制hexo源码到`hexo`目录下



docker-compose.yml 内容如下

```
version: '3'
services:
  hexo:
    image: denalon/hexo-run
    ports: 
      - "4000:4000"
    environment:
      - PGID=1000
      - PUID=1000
      - TZ=Asia/Shanghai
    volumes:
      - ./run.sh:/run.sh
      - ./hexo:/hexo
    entrypoint:
      - sh
      - /run.sh
```

run.sh 内容如下

```
npm install
hexo generate
hexo server
```
### run 运行

run `docker-compose up`or`docker-compose up -d`

在项目根目录下执行 `docker-compose up`或者`docker-compose up -d`


### other 其他功能

change  `run.sh`file to run other hexo orders