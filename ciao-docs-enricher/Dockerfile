# Docker container for ciao-docs-enricher CIP
# Version 0.7
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-docs-enricher zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-docs-enricher/ws/ciao-docs-enricher/target/ciao-docs-enricher-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-docs-enricher
RUN unzip ciao-docs-enricher-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-docs-enricher
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-docs-enricher/ciao-docs-enricher-1.0.0-SNAPSHOT/config
# Standard ciao configuration file folder
VOLUME ["/root/.ciao"]
# Static JSON folder
VOLUME ["/opt/ciao-docs-enricher/json"]
# In-progress folder
VOLUME ["/opt/ciao-docs-enricher/in-progress"]
# Jolokia Agent port
EXPOSE 8778
# Entry point
ENTRYPOINT ["/opt/ciao-docs-enricher/ciao-docs-enricher-1.0.0-SNAPSHOT/run.sh"]