# Docker container for ciao-docs-parser CIP
# Version 0.9
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-docs-parser zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-docs-parser/ws/ciao-docs-parser/target/ciao-docs-parser-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-docs-parser
RUN unzip ciao-docs-parser-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-docs-parser
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-docs-parser/ciao-docs-parser-1.0.0-SNAPSHOT/config
# Standard ciao configuration file folder
VOLUME ["/root/.ciao"]
# Input file folder
VOLUME ["/opt/ciao-docs-parser/input"]
# Error file folder
VOLUME ["/opt/ciao-docs-parser/error"]
# In-progress file folder
VOLUME ["/opt/ciao-docs-parser/in-progress"]
# Jolokia Agent port
Expose 8778
# Hazelcast port
Expose 5701
# Entry point
ENTRYPOINT ["/opt/ciao-docs-parser/ciao-docs-parser-1.0.0-SNAPSHOT/run.sh"]