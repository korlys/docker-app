
### sscms配置mysql数据库的部署


### 环境变量配置
可以通过环境变量配置 SSCMS 运行参数：

SSCMS_SECURITY_KEY 必填项，SSCMS 客户端与服务器端加密通讯使用的秘钥，通常为 GUID 字符串

SSCMS_DATABASE_TYPE 必填项，SSCMS 使用的数据库类型，可以为以下取值中的一种：

`MySQL `： MySQL 数据库

`SQLServer` ： Microsoft SQLServer 数据库

`PostgreSQL` ： PostgreSQL 数据库

`SQLite` ： SQLite 数据库

SSCMS_DATABASE_HOST 数据库主机地址

SSCMS_DATABASE_PORT 数据库访问端口

SSCMS_DATABASE_USER 数据库用户名

SSCMS_DATABASE_PASSWORD 数据库密码

SSCMS_DATABASE_NAME 数据库库名

SSCMS_DATABASE_CONNECTION_STRING 数据库连接字符串

SSCMS_REDIS_CONNECTION_STRING Redis 缓存连接字符串



如果 SSCMS_DATABASE_TYPE 设置为 SQLite 本地数据库，数据库将存储在 wwwroot/sitefiles/database.sqlite 文件中，如果 SSCMS_DATABASE_TYPE 设置为其他数据库类型，则还需要设置数据库环境变量。

数据库环境变量可以通过指定 SSCMS_DATABASE_HOST、SSCMS_DATABASE_PORT、SSCMS_DATABASE_USER、SSCMS_DATABASE_PASSWORD 以及 SSCMS_DATABASE_NAME 进行设置，也可以通过 SSCMS_DATABASE_CONNECTION_STRING 直接设置，两种方式选择其中一种

### 安装 SS CMS 系统

如果在云服务器环境中安装，请先配置安全组，确保网站地址及端口能够被外网访问。

打开浏览器，访问地址 http://<IP地址或域名>/ss-admin/install，进入 SS CMS 系统安装界面：


```
services:
  sqlserver:
     image: mcr.microsoft.com/mssql/server:2017-latest
     container_name: sqlserver
     restart: always
     privileged: true
     networks:
      - sqlserver
     volumes:
      - ./app/data:/var/opt/mssql/data
      - ./app/log:/var/opt/mssql/log
      - ./app/secrets:/var/opt/mssql/secrets 
     ports:
      - 1433:1433
     environment:
      - "USER_UID=1000"
      - "USER_GID=1000"
      - "ACCEPT_EULA=Y"
      - "SA_PASSWORD=p@ssword123456"

```

[sql on docker](https://docs.microsoft.com/zh-cn/sql/linux/tutorial-restore-backup-in-sql-server-container?view=sql-server-ver15)
使用mssql数据库时需要自行创建一个数据库，需要使用**对应版本**的ssms连接数据库创建。