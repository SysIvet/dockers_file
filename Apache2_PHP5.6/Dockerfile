FROM ubuntu:latest

RUN apt-get update && apt-get -yqq install software-properties-common

RUN add-apt-repository ppa:ondrej/php 
RUN apt-get --allow-unauthenticated update && apt-get --allow-unauthenticated -yqq install php5.6 php5.6-mbstring php5.6-mcrypt php5.6-mysql php5.6-xml

RUN apt-get -yqq install apache2

RUN echo "ServerName localhost" >> /etc/apache2/conf-enabled/servername.conf
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]

EXPOSE 80

