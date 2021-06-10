***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

***

## halo
java项目需要先下载halo的最新编译包.jar到项目根目录下


## java

使用docker方式打包

```
docker run -it --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean package
```