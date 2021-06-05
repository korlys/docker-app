## halo
java项目需要先下载halo的最新编译包.jar到项目根目录下


## java

使用docker方式打包

```
docker run -it --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean package
```