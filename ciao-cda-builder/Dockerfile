# Docker container for ciao-cda-builder CIP
# Version 0.6
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-cda-builder zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-cda-builder/ws/target/ciao-cda-builder-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-cda-builder
RUN unzip ciao-cda-builder-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-cda-builder
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-cda-builder/ciao-cda-builder-1.0.0-SNAPSHOT/config
# Standard ciao configuration file folder
VOLUME ["/root/.ciao"]
# In-progress folder
VOLUME ["/opt/ciao-cda-builder/in-progress"]
# Jolokia Agent port
EXPOSE 8778
# Entry point
ENTRYPOINT ["/opt/ciao-cda-builder/ciao-cda-builder-1.0.0-SNAPSHOT/run.sh"]