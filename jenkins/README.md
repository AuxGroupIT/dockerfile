AUX jenkins:2.7.2 & jenkins:2.7.2-plugins
======================================

使用方法
-----------

    docker pull 100.100.20.216/aux-pub/jenkins:2.7.2-plugins

    docker pull 100.100.20.216/aux-pub/jenkins:2.7.2

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