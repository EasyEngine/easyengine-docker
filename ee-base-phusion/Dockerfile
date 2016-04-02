#based image Ubuntu LTS
FROM phusion/baseimage
MAINTAINER Rahul Bansal <rahul.bansal@rtcamp.com>

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

# Fix debconf issue
ENV DEBIAN_FRONTEND noninteractive

# Fix tput: unknown terminal "unknown"
ENV TERM xterm

# Set Git Config
RUN echo '[user]' > /root/.gitconfig
RUN echo '  name = ee' >> /root/.gitconfig
RUN echo '  email = ee@example.com' >> /root/.gitconfig

# Install wget
RUN apt-get update && apt-get install -y wget

# Install EasyEngine
RUN wget -qO ee rt.cx/ee && sudo bash ee

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
