# Docker container for ciao-transport-dts CIP
# Version 0.4
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-transport-spine zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-transport-dts/ws/ciao-transport-dts/target/ciao-transport-dts-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-transport-dts
RUN unzip ciao-transport-dts-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-transport-dts
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-transport-dts/ciao-transport-dts-1.0.0-SNAPSHOT/config
# Jolokia Agent port
EXPOSE 8778
# Hazelcast Server port
EXPOSE 5703
# Standard ciao configuration file folder
VOLUME ["/root/.ciao/"]
# In-progress file folder
VOLUME ["/opt/ciao-transport-dts/in-progress"]
# DTS folder
VOLUME ["/opt/dts"]
# Ciao folder
VOLUME ["/opt/ciao-transport-dts"]
# Entry point
ENTRYPOINT ["/opt/ciao-transport-dts/ciao-transport-dts-1.0.0-SNAPSHOT/run.sh"]