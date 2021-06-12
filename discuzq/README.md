使用`docker-compose up`启动，访问 https://<域名>/install 就可以开始安装，并正常使用。使用`docker-compose up -d`后台运行。

如果未能提供nginx的ssl证书，需要将` - ./data/certs/:/etc/nginx/certs/`注释掉。映射nginx证书目录必须保证该目录下有相应的文件,SSL证书文件分别为discuz.crt 和 discuz.key。无此文件可能导致容器运行不正常。

MySQL Host：请输入`127.0.0.1`即可

MySQL 数据库：请输入`root`即可

MySQL 用户名：请输入`root`即可

MySQL 密码：请输入`root`即可

请参照[Discuz! Q 官方文档](https://discuz.com/docs/)