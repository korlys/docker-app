、环境变量配置
可以通过环境变量配置 SSCMS 运行参数：

SSCMS_SECURITY_KEY 必填项，SSCMS 客户端与服务器端加密通讯使用的秘钥，通常为 GUID 字符串

SSCMS_DATABASE_TYPE 必填项，SSCMS 使用的数据库类型，可以为以下取值中的一种：

MySQL ： MySQL 数据库
SQLServer ： Microsoft SQLServer 数据库
PostgreSQL ： PostgreSQL 数据库
SQLite ： SQLite 数据库
SSCMS_DATABASE_HOST 数据库主机地址

SSCMS_DATABASE_PORT 数据库访问端口

SSCMS_DATABASE_USER 数据库用户名

SSCMS_DATABASE_PASSWORD 数据库密码

SSCMS_DATABASE_NAME 数据库库名

SSCMS_DATABASE_CONNECTION_STRING 数据库连接字符串

SSCMS_REDIS_CONNECTION_STRING Redis 缓存连接字符串

如果 SSCMS_DATABASE_TYPE 设置为 SQLite 本地数据库，数据库将存储在 wwwroot/sitefiles/database.sqlite 文件中，如果 SSCMS_DATABASE_TYPE 设置为其他数据库类型，则还需要设置数据库环境变量。

数据库环境变量可以通过指定 SSCMS_DATABASE_HOST、SSCMS_DATABASE_PORT、SSCMS_DATABASE_USER、SSCMS_DATABASE_PASSWORD 以及 SSCMS_DATABASE_NAME 进行设置，也可以通过 SSCMS_DATABASE_CONNECTION_STRING 直接设置，两种方式选择其中一种