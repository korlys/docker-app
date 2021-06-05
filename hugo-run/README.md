**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

## config  配置

create  new file `docker-compose.yml ` `run.sh` and a folder `hugo`

创建新文件 `docker-compose.yml ` `run.sh` 和一个目录`hugo`

copy hugo source file to `hugo`folder

复制hexo源码到`hugo`目录下



docker-compose.yml 内容如下

```
version: '3'
services:
  hugo:
    image: denalon/hugo-run
    ports: 
      - "4000:4000"
    environment:
      - PGID=1000
      - PUID=1000
      - TZ=Asia/Shanghai
    volumes:
      - ./run.sh:/run.sh
      - ./hugo:/hugo
    entrypoint:
      - sh
      - /run.sh
```

run.sh 内容如下

```
hugo
```
### run 运行

run `docker-compose up`or`docker-compose up -d`

在项目根目录下执行 `docker-compose up`或者`docker-compose up -d`


### other 其他功能

change  `run.sh`file to run other hugo orders