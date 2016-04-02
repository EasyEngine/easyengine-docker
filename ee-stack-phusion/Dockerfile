#based image Ubuntu LTS
FROM easyengine/base-phusion
MAINTAINER Rahul Bansal <rahul.bansal@rtcamp.com>

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

# Install Web Stack using EasyEngine
RUN LC_ALL=en_US.UTF-8 ee stack install --web

# Running scripts during container startup
RUN mkdir -p /etc/my_init.d

# ee start
ADD ee.sh /etc/my_init.d/ee.sh

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
