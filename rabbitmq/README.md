# Redis

### 说明

基于官方3.7.15版

### 命令

* 创建容器并启动
```
docker pull rabbitmq:3.7.15

docker run -d --name rabbitmq \
--publish 5671:5671 --publish 5672:5672 --publish 4369:4369 \
--publish 25672:25672 --publish 15671:15671 --publish 15672:15672 \
rabbitmq:3.7.15
```

* 进入容器并开启管理功能：
```
docker exec -it rabbitmq /bin/bash
rabbitmq-plugins enable rabbitmq_management
```

* 启动/停止容器
```
docker start/stop 容器ID
```
