FROM jenkins:2.7.2

USER root

COPY plugins/ /usr/share/jenkins/ref/plugins/

COPY docker/ /usr/local/bin/

RUN chmod +x /usr/local/bin/docker