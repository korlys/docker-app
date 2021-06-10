
***

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目


***
### 直接运行


这些项目均可以在其目录下执行`docker-compose up`执行

根据运行需要修改端口号和目录映射



### 注意事项

部分项目需要下载程序压缩包，并解压缩到对应目录

部分项目需要对项目目录权限设置成777

部分项目在运行时需要自动使用docker build，从而导致构建时间过长