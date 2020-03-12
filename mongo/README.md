# Redis

### 说明

基于官方3.2.21版

### 命令

* 创建容器并启动
```
docker run -d --name mongo_3.2.21_dev -p 27017:27017 --privileged=true -v /data/volume/mongo:/data/db -d mongo:3.2.21
```

* 参数说明
  1. --name mongo_3.2.21_dev 容器的名字  
  2. -p 27017:27017：暴露本机27017端口（冒号前）连接到容器内27017端口（冒号后）   
  3. --privileged=true：容器内的root拥有真正root权限，否则容器内root只是外部普通用户权限  
  4. -v /data/volume/mongo:/data：映射数据目录

* 进入容器伪交互console
```
docker exec -it mongo_3.2.21_dev bash
```

* 启动/停止容器
```
docker start/stop 容器ID
```
