# Centos based container with Java and Tomcat
FROM centos:7
MAINTAINER SKonotop

# Install prepare infrastructure
RUN yum update -y && \
    yum install java-1.8.0-openjdk-devel -y && \
    yum install wget -y && \
    yum install unzip -y

ENV TOMCAT_VER apache-tomcat-8.5.31

# Install Tomcat
RUN cd /tmp && \
    wget http://apache.volia.net/tomcat/tomcat-8/v8.5.31/bin/$TOMCAT_VER.zip && \
    unzip $TOMCAT_VER.zip -d /opt && \
    rm -f apache*.zip && \
    chmod +x /opt/$TOMCAT_VER/bin/*.sh
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.171-7.b10.el7.x86_64/jre
ENV JAVA_OPTS -Djava.security.egd=file:///dev/urandom
ENV CATALINA_BASE /opt/$TOMCAT_VER
ENV CATALINA_HOME /opt/$TOMCAT_VER
ENV CATALINA_PID /opt/$TOMCAT_VER/temp/tomcat.pid
ENV CATALINA_OPTS -Xms512M -Xmx1024M -server -XX:+UseParallelGC
WORKDIR /opt/$TOMCAT_VER/bin
EXPOSE 8080
