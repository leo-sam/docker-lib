# Kafka, Zookeeper, Kakfa-manager


* 基础镜像
```
wurstmeister/kafka  
wurstmeister/zookeeper  
sheepkiller/kafka-manager  
```

* 修改yml文件中的ip地址为本机的本地局域网ip（例如192.168.0.100）


* 启动容器，在yml文件所在目录，也可以添加参数 -f /path/to/compose-server.yml
``` 
local> docker-compose up -d
```


* 进入容器创建Topic
```
local> docker exec -it 容器ID /bin/bash  
bash-4.4> cd /opt/kafka  
bash-4.4> ./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic test  
```


* 显示出下面字样表示创建成功
```
Created topic "test".  
```

* 启动生产者
```
bash-4.4> ./bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
```


* 另开终端窗口启动消费者
```
local>docker exec -it 容器ID /bin/bash
bash-4.4> cd /opt/kafka
bash-4.4> ./bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```


* 执行完上诉命令后，在生产者窗口中 输入任意内容回车，即可在消费者的窗口查看到消息


* 浏览器访问http://localhost:19000 将会显示显示kafka-manager界面，添加kafka节点(本机ip:2181)后，可显示上面创建的test主题
