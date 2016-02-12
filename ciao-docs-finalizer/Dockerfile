# Docker container for ciao-docs-finalizer CIP
# Version 0.5
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk wget unzip
# Get ciao-docs-finalizer zipped binary
RUN wget http://hcdn-build1.cloudapp.net/view/CIAO/job/ciao-docs-finalizer/ws/target/ciao-docs-finalizer-1.0.0-SNAPSHOT-bin.zip
# Unzip into /opt/ciao-docs-finalizer
RUN unzip ciao-docs-finalizer-1.0.0-SNAPSHOT-bin.zip -d /opt/ciao-docs-finalizer
# Copy log4j.properties file into config folder
COPY log4j.properties /opt/ciao-docs-finalizer/ciao-docs-finalizer-1.0.0-SNAPSHOT/config
# Standard ciao configuration file folder
VOLUME ["/root/.ciao"]
# In-progress file folder
VOLUME ["/opt/ciao-docs-finalizer/in-progress"]
# Error file folder
VOLUME ["/opt/ciao-docs-finalizer/error"]
# Completed file folder
VOLUME ["/opt/ciao-docs-finalizer/completed"]
# Jolokia Agent port
EXPOSE 8778
# Hazelcast Server port
EXPOSE 5702
# Entry point
ENTRYPOINT ["/opt/ciao-docs-finalizer/ciao-docs-finalizer-1.0.0-SNAPSHOT/run.sh"]