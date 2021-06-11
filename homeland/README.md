## Homeland Docker

[Homeland](https://homeland.ruby-china.org/) 基于 Docker 的自动化部署方案。

## Install Docker:
This script was made for Ubuntu Server 14.04, If you use other system version, please read Docker Installaction.
```
curl -sSL https://git.io/install-docker | bash
```
Run Docker commands without sudo

1. Add the docker group if it doesn't already exist
```
$ sudo groupadd docker
```
2. Add the connected user $USER to the docker group

Optionally change the username to match your preferred user.
```
$ sudo gpasswd -a $USER docker
```
3. Restart the docker daemon
```
$ sudo service docker restart
```
If you are on Ubuntu 14.04-15.10, use docker.io instead:
```
$ sudo service docker.io restart
```

### Test Docker

```

docker info
docker-compose version
```
Get homeland-docker
```
git clone https://github.com/ruby-china/homeland-docker.git

cd homeland-docker/

```
Application configuration
Homeland use app.local.env file to config, there have an example in app.default.env. You must read the Configuration and customize the config variables with your application.

Required settings

Please edit app.local.env file:
```
# For auto SSL get cert
domain=your-host.com
# default: admin@admin.com, when you use this email register a user, you will get the admin role.
# Or you can change it as your email.
admin_emails=admin@admin.com
```
Install
```
make install
```
Startup
```
make start
```
Now, you can visit https://your-host.com

### 登录和配置
使用配置的admin_email的邮箱注册，配置管理员账号和密码。通过/admin进去程序后台

### Commands
Command	Desc
```
make install	For first install, create database
make update	Update docker image and restart application for update
make start	Startup application
make stop	Stop application containers (except Database, Redis)
make restart	Restart application
make status	Show container status
make console	Enter the Rails console
make stop-all	Stop all services (including Databse, Redis)
make reindex	Rebuild Search indexes
```

## 系统需求

- Linux Server [4 Core CPU, 4G Memory, 50G Disk, 64 位] - _建议 Ubuntu Server 14.04_
- [Docker](https://www.docker.com/), [Docker Compose](https://docs.docker.com/compose/)
- [Aliyun OSS](https://www.aliyun.com/product/oss) 或 [UpYun](https://www.upyun.com) 用于文件存储。

## 使用说明

https://homeland.ruby-china.org/install/

## Versions

分支对应 Homeland 版本

- master - hoemland/homeland:3-8-latest
- 3-8-stable - hoemland/homeland:3-8-latest
- 3-7-stable - hoemland/homeland:3-7-latest
- 3-3-stable - hoemland/homeland:3-3-latest
