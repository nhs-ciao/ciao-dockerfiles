# Docker container for ciao-transport-spine CIP
# Version 0.6
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-transport-spine zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-transport-spine/ws/target/ciao-transport-spine-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-transport-spine
RUN unzip ciao-transport-spine-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-transport-spine
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-transport-spine/ciao-transport-spine-1.0.0-SNAPSHOT/config
# Standard TCP listen port for incoming messages from SPINE
EXPOSE 8122
# Jolokia Agent port
EXPOSE 8778
# Hazelcast Server port
EXPOSE 5704
# Standard ciao configuration file folder
VOLUME ["/root/.ciao/"]
# Keystores folder
VOLUME ["/opt/keystores/"]
# In-progress file folder
VOLUME ["/opt/ciao-transport-spine/in-progress"]
# Entry point
ENTRYPOINT ["/opt/ciao-transport-spine/ciao-transport-spine-1.0.0-SNAPSHOT/run.sh"]