# Docker container for ciao-docs-transformer CIP
# Version 0.1
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-docs-transformer zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-docs-transformer/ws/target/ciao-docs-transformer-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-docs-transformer
RUN unzip ciao-docs-transformer-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-docs-transformer
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-docs-transformer/ciao-docs-transformer-1.0.0-SNAPSHOT/config
# Standard ciao configuration file folder
VOLUME ["/root/.ciao"]
# In-progress folder
VOLUME ["/opt/ciao-docs-transformer/in-progress"]
# Jolokia Agent port
EXPOSE 8778
# Entry point
ENTRYPOINT ["/opt/ciao-docs-transformer/ciao-docs-transformer-1.0.0-SNAPSHOT/run.sh"]