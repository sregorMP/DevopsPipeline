FROM jenkins/jenkins:alpine

MAINTAINER Rogers Machado Paiva

USER root

RUN mkdir -p /opt/maven && \ 
    cd /opt/maven && \ 
    wget http://ftp.unicamp.br/pub/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.tar.gz && \
    tar -xzvf apache-maven-3.6.2-bin.tar.gz && \
    mv apache-maven-3.6.2 apache-maven 

USER jenkins
