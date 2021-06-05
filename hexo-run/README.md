
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