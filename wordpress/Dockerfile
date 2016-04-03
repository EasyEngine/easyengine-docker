#based image Ubuntu LTS
FROM easyengine/stack-phusion
MAINTAINER Rahul Bansal <rahul.bansal@rtcamp.com>

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

# Add Volumes for data
VOLUME  ["/var/www", "/var/lib/mysql","/var/log"]
RUN chown -R mysql:mysql /var/lib/mysql
RUN chown -R www-data:www-data /var/www
RUN chown -R root:syslog /var/log

# Add Volumes for config
# VOLUME  ["/etc/nginx","/etc/php","/etc/mysql", "/etc/postfix","/etc/ee"]

# Install Web Stack using EasyEngine
RUN LC_ALL=en_US.UTF-8 ee site create `hostname -f` --wpredis

# Running scripts during container startup
RUN mkdir -p /etc/my_init.d

# ee start
ADD ee.sh /etc/my_init.d/ee.sh

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
