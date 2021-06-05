
### 简介 docker-Compose 

>Compose 中有两个重要的概念：
>+ 服务 (service)：一个应用的容器，实际上可以包括若干运行相同镜像的容器实例。
>+ 项目 (project)：由一组关联的应用容器组成的一个完整业务单元，在 docker-compose.yml 文件中定义。

### 使用 Usage

直接在项目根目录启动 docker-compose 即可：

```bash
sudo docker-compose up -d
```

### 数据卷 volume

>数据卷 是一个可供一个或多个容器使用的特殊目录，它绕过 UFS，可以提供很多有用的特性：
>+ 数据卷 可以在容器之间共享和重用
>+ 对 数据卷 的修改会立马生效
>+ 对 数据卷 的更新，不会影响镜像
>+ 数据卷 默认会一直存在，即使容器被删除

#### mysql容器使用的数据卷

设置数据库的 volume 能够将数据保存在服务器而非容器中，避免因删除容器或者修改 Dockerfile/docker-compose.yml 导致的数据丢失。

```yaml
volumes:
  - ./mysql:/var/lib/mysql
```

#### 应用程序使用的数据卷

设置 应用程序的 volume 以防因安装不兼容插件导致的程序无法运行，一旦出现这种情况，只需将对应目录下的插件删除即可恢复。



```yaml
volumes:
  - ./wordpress:/var/www/html
  - ./favicon.ico:/var/www/html/favicon.ico
  - ./uploads.ini:/usr/local/etc/php/conf.d/uploads.ini
```

### 端口设置 ports

**数据库端口**

MySql 默认端口 3306

**应用程序端口**

映射服务器端口到容器内部的端口，假设服务器ip地址是 192.168.1.0 的话，我们可以通过 192.186.1.0:8000 访问 container 的 80 端口

```yaml
ports:
  - "8000:80"
```

#### Nginx 反向代理

如果需要为网站设置域名，则可以使用下面配置。`proxy_pass` 对应的 8000 端口要和 wordpress 容器向外映射的端口保持一致。

```conf
server {
  listen      80;
  server_name xxx.com;

  client_max_body_size    20m;

  location / {
    proxy_pass http://localhost:8000;
    proxy_set_header Host $host;
    proxy_set_header X-Forward-For $remote_addr;
  }
}
```

[返回目录 :arrow_heading_up:](#目录-TOC)


### 常用命令 Command

#### 镜像相关命令

+ 列出所有镜像

```bash
docker image ls
```

+ 删除镜像

```bash
docker image rm <image-name>
```

#### 容器相关命令

+ 基于镜像新建一个容器并启动



#### Compose 相关命令

Compose 命令都是针对项目的，因此需要在项目目录下也就是 docker-compose.yml 文件所在目录下执行。

+ 前台启动

所有启动的容器都在前台，控制台将会同时打印所有容器的输出信息，可以很方便进行调试。当通过 `Ctrl-C` 停止命令时，所有容器将会停止。

```bash
docker-compose up
```

+ 后台启动

在后台启动并运行所有的容器，一般推荐生产环境下使用该选项。

```bash
docker-compose up -d
```

+ 停止

停止已经处于运行状态的容器，但不删除它。通过 `docker-compose start` 可以再次启动这些容器。

```bash
docker-compose stop
```

+ 启动

启动已经存在的服务容器。

```bash
docker-compose start
```

+ 删除

删除所有（停止状态的）服务容器。推荐先执行 docker-compose stop 命令来停止容器。

选项：
+ -f, --force 强制直接删除，包括非停止状态的容器。一般尽量不要使用该选项。
+ -v 删除容器所挂载的数据卷。

```bash
docker-compose rm
```

+ 列出**项目中**的所有容器

```bash
docker-compose ps
```


#### 数据卷相关命令

+ 列出所有数据卷

```bash
docker volume ls
```

+ 查看指定数据卷

```bash
docker inspect <volume-name>
```

+ 删除数据卷

```bash
docker volume rm <volume-name>
```

+ 删除无主的数据卷

```bash
docker volume prune
```
