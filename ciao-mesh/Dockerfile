# Docker container for ciao-mesh
# This is the test client
# Version 0.1
FROM ubuntu:14.04
MAINTAINER HSCIC
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk unzip wget
# Get mesh client
RUN wget http://systems.hscic.gov.uk/ddc/mesh/test-client/mesh-6.0.0.jar
# Create mesh install values in a file
RUN echo '1\n\n1\n1\n1\n\nO\n1\n1\n1\nY\n\n' >> install-values.txt
# Install mesh client
RUN java -jar mesh-6.0.0.jar < install-values.txt
# Create directory for configuration files
RUN mkdir /usr/local/MESH-CONFIG
# Configuration file volume
VOLUME ["/usr/local/MESH-CONFIG"]
# Keystore volume
VOLUME ["/usr/local/MESH-APP-HOME/KEYSTORE"]
# Mailbox volume
VOLUME ["/usr/local/MESH-DATA-HOME"]
# Entrypoint to container
ENTRYPOINT ["java", "-Dlog4j.configuration=file:/usr/local/MESH-APP-HOME/log4j.xml", "-jar", "/usr/local/MESH-APP-HOME/meshClient.jar", "/usr/local/MESH-CONFIG/meshclient.cfg"]
