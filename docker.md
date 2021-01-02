//linux内核3.10以上
uname -r

//安装
yum install docker

//启动
systemctl start docker

//版本
docker -v

//开机启动
systemctl enable docker

//停止
systemctl stop docker

//重启
service docker restart

//状态
systemctl status docker

1、搜索镜像
[root@localhost ~]# docker search tomcat
2、拉取镜像
[root@localhost ~]# docker pull tomcat

列出所有镜像
docker images
3.删除镜像，通过image的id来指定删除谁
docker rmi <image id>
3、根据镜像启动容器(-d：后台  -p：暴露端口)
docker run --name mytomcat -d tomcat:latest
4、查看运行中的容器
docker ps
5、 停止运行中的容器
docker stop  容器的id
6、查看所有的容器
docker ps -a
7、启动容器
docker start 容器id
8、删除一个容器
 docker rm 容器id
9、启动一个做了端口映射的tomcat
[root@localhost ~]# docker run -d -p 8888:8080 tomcat
-d：后台运行
-p: 将主机的端口映射到容器的一个端口    主机端口:容器内部的端口

10、为了演示简单关闭了linux的防火墙
service firewalld status ；查看防火墙状态
service firewalld stop：关闭防火墙
11、查看容器的日志
docker logs container-name/container-id

更多命令参看
https://docs.docker.com/engine/reference/commandline/docker/
可以参考每一个镜像的文档

//镜像慢
https://blog.csdn.net/weixin_43569697/article/details/89279225

//创建myrabbitmq
docker run -d -p 5672:5672 -p 15672:15672 --name myrabbitmq 7aae48fa6ef6

//案例里的镜像版本
docker.io/rabbitmq   3-management        7aae48fa6ef6        32 hours ago        179 MB
docker.io/tomcat     latest              7123ec940c88        9 days ago          510 MB
docker.io/redis      latest              bb0ab8a99fe6        9 days ago          95 MB
docker.io/mysql      5.7                 a1aa4f76fab9        4 weeks ago         373 MB

//删除所以镜像
https://www.imooc.com/article/details/id/32810

//安装elastic
docker run -e ES_JAVA_OPTS="-Xms256m -Xmx256m" -d -p 9200:9200 -p 9300:9300 --name ES01 5acf0e8da90b

==================

## 一个改变世界的“箱子”
https://juejin.cn/post/6906398071597301774

## 还在使用第三方Docker插件？SpringBoot官方插件真香！
https://juejin.cn/post/6904054246207913998

## 还在百度Docker命令？推荐一套我用起来特顺手的命令！
https://juejin.cn/post/6895888125886332941