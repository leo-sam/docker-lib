# Redis

### 说明

基于官方1.10版


### 命令

* 创建容器并启动
```
docker run -p 80:80 --name nginx \
-v /data/volume/nginx/html:/usr/share/nginx/html \
-v /data/volume/nginx/logs:/var/log/nginx  \
-d nginx:1.10

docker run -v /data/volume/nginx/conf.d:/etc/nginx/conf.d openresty/openresty:alpine
```

* 将容器内的配置文件拷贝到指定目录：
```
docker container cp nginx:/etc/nginx /data/volume/nginx/
cd /data/volume/nginx/
mv nginx conf
```
* 删除之前容器，再次启动
```
docker run -p 80:80 --name nginx \
-v /data/volume/nginx/html:/usr/share/nginx/html \
-v /data/volume/nginx/logs:/var/log/nginx  \
-v /data/volume/nginx/conf:/etc/nginx \
-d nginx:1.10
```

* 启动/停止容器
```
docker start/stop 容器ID
```
