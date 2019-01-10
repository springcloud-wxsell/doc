redis的启动：
$ docker run -d -p 6379:6379 redis:5.0.3

rabbitmq的启动
$ docker run -d --hostname my-rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.7.8-management

zipkin的启动
$ docker run -d -p 9411:9411 openzipkin/zipkin

rancher的启动
$ sudo docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:stable

构建镜像
$ docker build -t hub.c.163.com/job4ww/springcloud-eureka .

推送镜像
$ docker push hub.c.163.com/job4ww/springcloud-eureka

查看启动日志
# Tail the logs to show Rancher
$ sudo docker logs -f <CONTAINER_ID>

文件同步链接
# ln -s 绝对路径 绝对路径
$ ln -s /etc/systemd/system/tomcat.service /etc/systemd/system/multi-user.target.wants/tomcat.service

查看服务情况
docker ps | grep servicename
