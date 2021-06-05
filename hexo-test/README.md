### 自行构建的hexo运行容器 

### 容器里运行hexo

### 版本1

修改docker-compose.yml里的
```  
    environment: 
      - PUBLIC_HEXO_GITHUB_URL=https://xxxx.git
```
将xxx.git替换为自己的hexo源码仓库地址


### 版本2

将hexo项目放到项目目录下hexo文件夹

你可以使用git clone xxx.git hexo

### 配置项

run.sh文件是选取hexo源码以后执行的动作，可以加入hexo -d 执行远程推送