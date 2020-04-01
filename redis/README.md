# Redis

### 说明

基于官方4.0.14版


### 命令

* 创建容器并启动
```
docker run -d --name redis -p 6379:6379 --privileged=true -v /data/volume/redis:/data  -d redis:4.0.14 redis-server --appendonly yes
```

* 参数说明
  1. --name redis_4.0.14_dev 容器的名字  
  2. -p 6379:6379：暴露本机6379端口（冒号前）连接到容器内6379端口（冒号后）   
  3. --privileged=true：容器内的root拥有真正root权限，否则容器内root只是外部普通用户权限  
  4. -v /data/volume/redis:/data：映射数据目录

* 进入容器伪交互console
```
docker exec -it redis_4.0.14_dev bash
```

* 启动/停止容器
```
docker start/stop 容器ID
```
