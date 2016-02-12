# Docker container for ciao-elk
# Version 0.1
FROM willdurand/elk
MAINTAINER HSCIC
# Standard Elastic listen port
EXPOSE 9200
# Standard syslog listen port
EXPOSE 514

CMD [ "/usr/bin/supervisord", "-n", "-c", "/etc/supervisor/supervisord.conf" ]
