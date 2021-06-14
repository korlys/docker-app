***
**TEST**

本文档仅供测试和开发使用

**docker-compose项目**

运行本文档代码需要安装[docker](https://www.runoob.com/docker/docker-tutorial.html)和[docker-compose](https://www.runoob.com/docker/docker-compose.html)

下载该项目目录下的相应文件，执行`docker-compose up`运行项目，或通过`docker-compose up -d`后台运行项目。通过`docker-compose down`停止项目

***

Application Setup
The default username is admin@admin.com with the password of password, access the container at http://dockerhost:6875.

This application is dependent on a MySQL database be it one you already have or a new one. If you do not already have one, set up our MariaDB container here https://hub.docker.com/r/linuxserver/mariadb/.

If you intend to use this application behind a subfolder reverse proxy, such as our SWAG container or Traefik you will need to make sure that the environment variable is set to your external domain, or it will not workAPP_URL

Documentation for BookStack can be found at https://www.bookstackapp.com/docs/

Advanced Users (full control over the .env file)
If you wish to use the extra functionality of BookStack such as email, Memcache, LDAP and so on you will need to make your own .env file with guidance from the BookStack documentation.

When you create the container, do not set any arguments for any SQL settings. The container will copy an exemplary .env file to /config/www/.env on your host system for you to edit.

PDF Rendering
wkhtmltopdf is available to use as an alternative PDF rendering generator as described at https://www.bookstackapp.com/docs/admin/pdf-rendering/.

The path to wkhtmltopdf in this image to include in your .env file is ./usr/bin/wkhtmltopdf