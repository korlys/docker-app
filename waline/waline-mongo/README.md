***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行以下步骤

***

执行`docker-compose up -d`(或者执行`docker-compose up`后再另一个窗口执行下列操作)

### 数据库部分

使用`docker ps`查看正在运行的容器，

使用docker命令`docker run -it mongo /bash`进入mongo容器

直接使用`mongo`登录以后，查询命令会提示

```
uncaught exception: Error: command usersInfo requires authentication :
```

验证登录

```bash
 mongo -u root -p testtest -authenticationDatabase "admin"
```

显示数据库
```bash
show dbs
```

新建数据库

```bash
use waline
```

加入用户

```bash
db.createUser(
{
    user : "dev",
    pwd : "example",
    roles: [ { role : "readWrite", db : "waline" } ,
             { role : "dbAdmin", db : "waline" } ,
             { role : "userAdmin", db : "waline" }  
           ]
    }
)

```

显示该数据库用户

```bash
show users
```

新建的数据库没有数据使用`show dbs`并不会显示出来

使用以下命令随便往数据库里写入数据

```bash
db.check.insertOne({"ClientName":"John"});
```

再使用`show dbs`就会显示waline数据库


使用`exit`退出mongo，再次使用`exit`退出容器

### waline

访问http://ip:8360使用waline或在页面上加入该js代码使用waline

```
  <script>
    Waline.init({
      el: '#waline',
      serverURL: 'https://服务器地址',
    });
  </script>
```