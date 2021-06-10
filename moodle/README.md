***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***

### moodle

#### 使用方式

下载moodle压缩包，解压缩到当前目录下，然后修改配置文件里的目录映射地址

使用`docker-compose up -d` 运行，然后将生成的目录权限设置成777