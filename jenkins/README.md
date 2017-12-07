AUX jenkins:2.7.2 & jenkins:2.7.2-plugins
======================================

使用方法
-----------

镜像地址

    docker pull 100.100.20.216/aux-pub/jenkins:2.7.2-plugins

    docker pull 100.100.20.216/aux-pub/jenkins:2.7.2

启动方法：

```
docker run -p 8080:8080 -p 50000:50000 \
-d -v /var/run/docker.sock:/var/run/docker.sock \
-v /var/jenkins_home:/var/jenkins_home -e JAVA_OPTS="-Xmx768m" \
-e JAVA_OPTS=-Duser.timezone=Asia/Shanghai \
--name aux-jenkins  100.100.20.216/aux-pub/jenkins:2.7.2-plugins
```


2.7.2-plugins 镜像Dockfile说明
-----------

```
FROM jenkins:2.7.2

USER root

COPY plugins/ /usr/share/jenkins/ref/plugins/

COPY docker/ /usr/local/bin/

RUN chmod +x /usr/local/bin/docker
```

**为了能在jenkins内使用docker命令，直接使用root用户权限**

**加入了大部分常用镜像，大约100M+，没有上传，源码内使用了两个git插件作为例子**