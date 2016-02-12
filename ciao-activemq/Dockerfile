# Docker container for ciao-activemq
# Version 0.5
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk unzip wget
# Get ActiveMQ
RUN wget http://mirror.catn.com/pub/apache/activemq/5.12.1/apache-activemq-5.12.1-bin.tar.gz
# Extract the files from the gzip file to /opt/apache-activemq-5.12.1
RUN tar zxvf apache-activemq-5.12.1-bin.tar.gz -C /opt
# Move /opt/apache-activemq-5.12.1 to /opt/activemq
RUN mv /opt/apache-activemq-5.12.1 /opt/activemq
# Configuration folder
VOLUME ["/opt/activemq/conf"]
# Data folder
VOLUME ["/opt/activemq/data"]
# Standard ActiveMQ Web console listen port
EXPOSE 8161
# Standard ActiveMQ TCP listen port
EXPOSE 61616
# ActiveMQ Replication port
EXPOSE 61619
ENTRYPOINT ["bin/bash", "-c", "/opt/activemq/bin/activemq console"]
