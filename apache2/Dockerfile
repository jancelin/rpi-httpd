FROM resin/rpi-raspbian:latest
MAINTAINER  Julien Ancelin 
            
RUN apt-get -y update && \
    apt-get install -y apache2 vim

RUN a2enmod proxy proxy_http
# Copy config site available
ADD reach.conf /etc/apache2/sites-available/000-default.conf

RUN a2ensite 000-default.conf

EXPOSE 80

#Start apache2
ADD start.sh /start.sh
RUN chmod 0755 /start.sh
CMD /start.sh
