***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***

## hellohao内部版

### 说明

**需要**自行下载最新的编译包

**需要**自行上传sql文件到数据库

**不需要**本机安装java环境，php环境

**不需要**本机安装mysql数据库

### 使用步骤

第一步. 在https://github.com/Hello-hao/Tbed 下载源文件或者编译包，将jar文件放到app目录下

由于jar文件太大，本文档并未收集此文件。


第二步. 初次运行，需要将hellohao的镜像代码注释掉（可选）,然后运行使用`docker-compose up`命令启动容器

```
 # hellohao:  《注释从此处开始
 #  image: maven:3.3-jdk-8
 #  command: [
 #      './hellohao',
 #      'java',
 #      '-jar',
 #      'Tbedmain'
 #       ]    《注释到此处结束
```

**不注释掉代码将导致程序频繁报错**但不影响关键步骤，可忽略。

第三步. 访问phpmyadmin页面http://127.0.0.1:9180 (本文档使用的地址)，登录mysql数据库，将sql数据库文件导入`picturebed`数据库中。

请注意，此处填写phpmyadmin连接mysql服务器时，使用地址为**mysqlserver**即`container_name: mysqlserver`的值，数据库服务器地址不是localhost或者127.0.0.1

第四步. 关闭数据库管理页面，使用`docker-compose down`关闭容器，将**第2步**的注释代码取消注释

第五步. 正式运行项目`docker-compose up`或`docker-compose up -d`


### 说明


 下载源文件或者编译包,如果需要覆盖application.properties文件需要保留数据库的默认连接参数

```
#数据库账号
spring.datasource.username=hellohao  #hellohao 需要跟mysql容器的用户名`MYSQL_USER`一致，也可以使用root账号登录
#数据库密码test
spring.datasource.password=hellohao  #hellohao 需要跟mysql容器的用户密码`MYSQL_PASSWORD`一致，也可以使用`MYSQL_ROOT_PASSWORD`root密码123456
#数据库链接地址
spring.datasource.url=jdbc:mysql://mysqlserver:3306/picturebed?useUnicode=true&characterEncoding=utf8&serverTimezone=GMT%2B8  # mysqlserver 为容器里mysql数据库的名称，可修改，需跟mysql容器的容器名一致。

#用户Key秘钥
HellohaoKey=#

```
key请自行获取