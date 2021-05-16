FROM jenkins/jenkins:alpine

MAINTAINER Rogers Machado Paiva

USER root

ENV M2=/opt/maven/apache-maven/bin
ENV M2_HOME=/opt/maven/apache-maven
ENV PATH=$PATH:$M2_HOME:$M2

RUN mkdir -p /opt/maven && \ 
    cd /opt/maven && \ 
    wget https://ftp.unicamp.br/pub/apache/maven/maven-3/3.8.1/binaries/apache-maven-3.8.1-bin.tar.gz && \
    tar -xzvf apache-maven-3.8.1-bin.tar.gz && \
    mv apache-maven-3.8.1 apache-maven 

USER jenkins
