### 使用官方安装脚本自动安装

#### 安装命令

```
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun

```

#### 国内 daocloud 一键安装命令

```
curl -sSL https://get.daocloud.io/docker | sh

```

### 配置docker

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




### Compose 安装

Linux 上我们可以从 Github 上下载它的二进制包来使用，最新发行的版本地址：https://github.com/docker/compose/releases。

#### 运行以下命令以下载 Docker Compose 的最新版本：

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

```

#### 将可执行权限应用于二进制文件：

```
sudo chmod +x /usr/local/bin/docker-compose

```

#### 创建软链：

```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

```

#### 测试是否安装成功：

```
docker-compose --version

```


### Docker


Docker 是一个用于开发，交付和运行应用程序的开放平台。Docker 使您能够将应用程序与基础架构分开，从而可以快速交付软件。借助 Docker，您可以与管理应用程序相同的方式来管理基础架构。通过利用 Docker 的方法来快速交付，测试和部署代码，您可以大大减少编写代码和在生产环境中运行代码之间的延迟。

1、快速，一致地交付您的应用程序
Docker 允许开发人员使用您提供的应用程序或服务的本地容器在标准化环境中工作，从而简化了开发的生命周期。

容器非常适合持续集成和持续交付（CI / CD）工作流程，请考虑以下示例方案：

您的开发人员在本地编写代码，并使用 Docker 容器与同事共享他们的工作。
他们使用 Docker 将其应用程序推送到测试环境中，并执行自动或手动测试。
当开发人员发现错误时，他们可以在开发环境中对其进行修复，然后将其重新部署到测试环境中，以进行测试和验证。
测试完成后，将修补程序推送给生产环境，就像将更新的镜像推送到生产环境一样简单。
2、响应式部署和扩展
Docker 是基于容器的平台，允许高度可移植的工作负载。Docker 容器可以在开发人员的本机上，数据中心的物理或虚拟机上，云服务上或混合环境中运行。

Docker 的可移植性和轻量级的特性，还可以使您轻松地完成动态管理的工作负担，并根据业务需求指示，实时扩展或拆除应用程序和服务。

3、在同一硬件上运行更多工作负载
Docker 轻巧快速。它为基于虚拟机管理程序的虚拟机提供了可行、经济、高效的替代方案，因此您可以利用更多的计算能力来实现业务目标。Docker 非常适合于高密度环境以及中小型部署，而您可以用更少的资源做更多的事情。