FROM marcuswubi/docker-ubuntu:14.04

MAINTAINER maviniciuus <maviniciuus@gmail.com>

RUN apt-get update && \
apt-get install -y apache2 supervisor && \
a2enmod rewrite && \
a2enmod proxy && \
a2enmod proxy_http

RUN mkdir -p /var/lock/apache2 /var/run/apache2 /var/log/supervisor

COPY ./supervisord.conf /etc/supervisor/conf.d/supervisord.conf

ADD apacheConfig.conf /etc/apache2/sites-enabled/000-default.conf

EXPOSE 80
CMD ["/usr/bin/supervisord"]
