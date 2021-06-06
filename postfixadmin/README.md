### postfixadmin的初始化安装

第一步，需要通过http://域名/setup.php


通过输入密码，获得管理员hash（Generate setup_password hash）

hash值事例如下：

```
$CONF['setup_password'] = '$2y$10$UkOf2dWBhDiOtH1BJ1.G.OzNxZ00Vn6n55ryPG9ieYqycelmQKU66';
```

而这个hash并不能直接用来登录，需要第二步操作

第二步，将生成的hash值添加到项目的配置文件config.local.php的文件里

将

```
$CONF['setup_password'] = 'changeme';
```
修改为
```
$CONF['setup_password'] = '$2y$10$UkOf2dWBhDiOtH1BJ1.G.OzNxZ00Vn6n55ryPG9ieYqycelmQKU66';
```
然后保存

第三步，再次登录http://域名/setup.php

登录 第一步**输入的密码** Login with setup_password

正式获得新建管理员账号和密码的权限

