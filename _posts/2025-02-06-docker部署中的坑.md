## *服务器部署Docker方法*

### 第一步：更新软件，获取相关依赖
````bash
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release
````

### 第二步：添加Docker的GPG密钥

````bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
````

### 第三步：安装docker引擎

````bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
````

### 第四步：配置docker镜像源

````bash
sudo nano /etc/docker/daemon.json

{
   "registry-mirrors": [
     "https://docker.hpcloud.cloud",
  "https://docker.m.daocloud.io",
  "https://docker.unsee.tech",
  "https://docker.1panel.live",
  "http://mirrors.ustc.edu.cn",
  "https://docker.chenby.cn",
  "http://mirror.azure.cn",
  "https://dockerpull.org",
  "https://dockerhub.icu",
  "https://hub.rat.dev",
  "https://proxy.1panel.live",
  "https://docker.1panel.top",
  "https://docker.m.daocloud.io",
  "https://docker.1ms.run",
  "https://docker.ketches.cn"
   ]
 }

````

重启docker,

````bash
sudo systemctl restart docker
````

### 第五步：开放云服务器端口

````bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw reload
````

### Docker常用操作命令

- **镜像（Image）管理**
- **容器（Container）管理**
- **网络（Network）管理**
- **数据卷（Volume）管理**
- **Docker Compose**

#### **docker镜像拉取**

````dockerfile
docker pull 镜像名[:tag]
````

例子:

````dockerfile
docker pull nginx          # 拉取最新版本的 Nginx
docker pull redis:6.2      # 拉取 Redis 6.2 版本
````

查看已经存在镜像

````dockerfile
docker images
````

删除镜像

````dockerfile
docker rmi 镜像ID/名称
````

查看镜像详细信息

````dockerfile
docker inspect 镜像ID/名称
````
#### **docker容器管理**
运行容器
```` dockerfile
docker run -d --name 容器名 -p 外部端口:容器端口 镜像名
````

查看运行容器

````dockerfile
docker ps
docker ps -a
````

停止容器

````dockerfile
docker stop 容器ID/名称
````

启停容器

````dockerfile
docker start 容器ID/名称
docker restart 容器ID/名称
````

删除

````dockerfile
docker rm 容器ID/名称
docker container prune

````

进入容器

````dockerfile
docker exec -it my-nginx bash
docker exec -it my-nginx sh
````

查看容器日志

````dockerfile
docker logs -f 容器ID/名称
````





#### **网络（Network）管理**

**查看 Docker 网络**

```dockerfile
docker network ls
```

 **创建自定义网络**

```dockerfile
docker network create mynetwork
```

**连接容器到网络**

```dockerfile
docker network connect mynetwork 容器名称
```

**断开容器的网络连接**

```dockerfile
docker network disconnect mynetwork 容器名称
```

**删除网络**

```dockerfile
docker network rm mynetwork
```

------

#### **4. 数据卷（Volume）管理**

**创建数据卷**

```dockerfile
docker volume create mydata
```

 **列出所有数据卷**

```dockerfile
docker volume ls
```

 **查看数据卷详细信息**

```dockerfile
docker volume inspect mydata
```

 **删除数据卷**

```dockerfile
docker volume rm mydata
```

 **运行容器时挂载数据卷**

```dockerfile
docker run -d --name my-container -v mydata:/app/data nginx
```

------

#### **5. Docker Compose（多容器编排）**

**启动容器**

在 `docker-compose.yml` 目录下运行：

```dockerfile
docker-compose up -d
```

 **停止容器**

```dockerfile
docker-compose down
```

**查看 Compose 容器日志**

```dockerfile
docker-compose logs -f
```
