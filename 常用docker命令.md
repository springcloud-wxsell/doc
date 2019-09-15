redis的启动：
$ docker run -d -p 6379:6379 redis:5.0.3

rabbitmq的启动
$ docker run -d --hostname my-rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.7.8-management

zipkin的启动
$ docker run -d -p 9411:9411 openzipkin/zipkin

rancher的启动
$ sudo docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:stable

elasticsearch的启动
$ docker run -d -p 9200:9200 -p 9300:9300 docker.elastic.co/elasticsearch/elasticsearch-oss:6.8.2

构建镜像
$ docker build -t hub.c.163.com/job4ww/springcloud-eureka .

推送镜像
$ docker push hub.c.163.com/job4ww/springcloud-eureka

Docker容器开机自动启动
  1. 在使用docker run启动容器时，使用--restart参数来设置：
    $ docker run -d -p 6379:6379 redis:5.0.3 --restart=always 
      --restart具体参数值详细信息：
        no -  容器退出时，不重启容器;

        on-failure - 只有在非0状态退出时才从新启动容器;

        always - 无论退出状态是如何，都重启容器;
       
      还可以在使用on - failure策略时，指定Docker将尝试重新启动容器的最大次数。默认情况下，Docker将尝试永远重新启动容器。
        $ sudo docker run --restart=on-failure:10 redis
        
  2. 如果已经启动的项目，则使用update更新：
    $ docker update --restart=always <containerid>

查看启动日志
# Tail the logs to show Rancher
$ sudo docker logs -f <CONTAINER_ID>

文件同步链接
# ln -s 绝对路径 绝对路径
$ ln -s /etc/systemd/system/tomcat.service /etc/systemd/system/multi-user.target.wants/tomcat.service

查看服务情况
docker ps | grep servicename
