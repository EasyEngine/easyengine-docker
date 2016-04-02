#based image Ubuntu LTS
FROM ubuntu:14.04
MAINTAINER Rahul Bansal <rahul.bansal@rtcamp.com>

## Set gitconfig file needed by EE
## COPY ../gitconfig /root/.gitconfig

# Fix debconf issue
ENV DEBIAN_FRONTEND=noninteractive

# Fix tput: unknown terminal "unknown"
ENV TERM xterm

# Avoid ERROR: invoke-rc.d: policy-rc.d denied execution of start.
RUN ln -sf /bin/true /sbin/initctl

# Install Git
RUN apt-get install -y git-core
RUN git config --global user.name "rtCamp"
RUN git config --global user.email admin@rtcamp.com

# Install wget
RUN apt-get install -y wget

# Add VOLUME for Webroot
# VOLUME  ["/var/www"]

# Add VOLUME for Nginx config
# VOLUME  ["/etc/nginx"]

# Add VOLUME for PHP config
# VOLUME  ["/etc/php"]

# Add VOLUMEs to allow backup of config and databases
# VOLUME  ["/etc/mysql", "/var/lib/mysql"]

# Add VOLUME for Postfix config
# VOLUME  ["/etc/postfix"]

# Add VOLUME for EE config
# VOLUME  ["/etc/ee"]

# Install EasyEngine
RUN wget -qO ee rt.cx/ee && sudo bash ee

# Source EasyEngien Autocompletion
CMD "source /etc/bash_completion.d/ee_auto.rc"

# Default command
CMD ["bash"]
