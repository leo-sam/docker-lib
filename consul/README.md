# Consul

基于 https://github.com/hashicorp/docker-consul 修改，源镜像使用了Alpine Linux

自定义修改:
* 使用阿里云的源
* 安装基础工具 curl bash tzdata tar unzip 
* 使用中国时区

使用方法可参考 https://hub.docker.com/_/consul/
* Build镜像
```
docker build -t consul:0.7.5-dev . 
```

* 启动容器
``` 
docker run -d --name=consul -p 8500:8500 -p 8300:8300 -p 8301:8301 -p 8302:8302 -p 8400:8400 -p 8600:8600 -e CONSUL_BIND_INTERFACE=eth0 镜像ID
```
