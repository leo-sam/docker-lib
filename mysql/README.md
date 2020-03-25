# MySQL

### 说明

基于官方5.7.23版 https://hub.docker.com/_/mysql/

修改：

1. 自定义my.cnf，修改默认mysql默认编码为utf8mb4
2. 挂载cnf文件与本地mysql数据文件目录
3. 镜像本身未做改动

### 命令

* 创建容器并启动
```
docker run -d --name mysql -p 3306:3306 --privileged=true -v /data/docker-lib/mysql/my.cnf:/etc/my.cnf -v /data/volume/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root mysql:5.7.23
```

* 参数说明
  1. --name mysql_5.7.23_dev 容器的名字  
  2. -p 3306:3306：暴露本机3306端口（冒号前）连接到容器内3306端口（冒号后）   
  3. --privileged=true：容器内的root拥有真正root权限，否则容器内root只是外部普通用户权限  
  4. -v /data/docker-lib/mysql/my.cnf:/etc/my.cnf：映射配置文件    
  5. -v /data/volume/mysql:/var/lib/mysql：映射数据目录  
  6. -e MYSQL_ROOT_PASSWORD=caiqiu502：指定root账户密码  

* 进入容器伪交互console
```
docker exec -it mysql_5.7.23_dev bash
```

* 启动/停止容器
```
docker start/stop 容器ID
```
