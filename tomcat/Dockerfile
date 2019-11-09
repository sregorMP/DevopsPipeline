FROM openjdk:14-jdk-alpine

MAINTAINER Rogers Machado Paiva

ENV PATH=$PATH:/opt/apache-tomcat-8.5.47/bin/

RUN cd /opt && \
    wget http://mirror.nbtelecom.com.br/apache/tomcat/tomcat-8/v8.5.47/bin/apache-tomcat-8.5.47.tar.gz && \
    tar -xvzf /opt/apache-tomcat-8.5.47.tar.gz 

COPY ./conf/tomcat-users.xml /opt/apache-tomcat-8.5.47/conf/tomcat-users.xml
COPY ./conf/context.xml /opt/apache-tomcat-8.5.47/webapps/host-manager/META-INF/context.xml
COPY ./conf/context.xml /opt/apache-tomcat-8.5.47/webapps/manager/META-INF/context.xml

EXPOSE 8080

ENTRYPOINT ["catalina.sh", "run"]

