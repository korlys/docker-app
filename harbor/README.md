Harbor is deployed as several Docker containers. You can therefore deploy it on any Linux distribution that supports Docker. The target host requires Docker, and Docker Compose to be installed.

### Hardware
The following table lists the minimum and recommended hardware configurations for deploying Harbor.

|  Resource  | Minimum  | Recommended  |
|  ----  | ----  | ----  |
|  CPU  | 2 CPU  |	 4 CPU |
| Mem | 4 GB | 8GB |
| Disk | 40GB | 160GB |

### Software
The following table lists the software versions that must be installed on the target host.

| Software | Version | Description |
|  ----  | ----  | ----  |
| Docker engine |Version 17.06.0-ce+ or higher |For installation instructions, see Docker Engine documentation |
| Docker Compose |Version 1.18.0 or higher |For installation instructions, see Docker Compose documentation |
| Openssl |Latest is preferred |Used to generate certificate and keys for Harbor |

### Network ports
Harbor requires that the following ports be open on the target host.

| Port | Protocol | Description |
|  ----  | ----  | ----  |
| 443 | HTTPS |	Harbor portal and core API accept HTTPS requests on this port. You can change this port in the configuration file. |
| 4443 | HTTPS |	Connections to the Docker Content Trust service for Harbor. Only required if Notary is enabled. You can change this port in the configuration file. |
| 80 | HTTP | Harbor portal and core API accept HTTP requests on this port. You can change this port in the configuration file. |


### Run the Installer Script


Run the Installer Script

```
sudo ./install.sh
```



```
docker login reg.yourdomain.com
docker push reg.yourdomain.com/myproject/myrepo:mytag
```




Restart Docker Engine.


```
systemctl restart docker

```

Stop Harbor.


```
docker-compose down -v

```

Restart Harbor.

```
docker-compose up -d

```