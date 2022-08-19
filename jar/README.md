***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***

**java包springboot包通用运行环境**

将jar文件放到app目录下，
```
services:
  springboot:
    image: openjdk:8u292-jdk-oraclelinux7 ##使用openjdk，可以根据需要使用其他jdk
    container_name: springboot
    environment:
      - USER_UID=1000
      - USER_GID=1000
    restart: always
    privileged: true
    networks:
      - springboot
    volumes:
      - ./app/app.jar:/app.jar   ##app.jar是示例包名，将app.jar改成自己项目响应的包名
      - /etc/localtime:/etc/localtime
    ports:
      - "9770:9090"
    command: [
        'java',
        '-jar',
        'app.jar'
        ]
```

