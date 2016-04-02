#based image Ubuntu LTS
FROM easyengine/base:latest
MAINTAINER Rahul Bansal <rahul.bansal@rtcamp.com>

# Install openssh and supervisor
RUN apt-get update && apt-get install -y openssh-server supervisor

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

# Install Web Stack using EasyEngine
RUN ee stack install --web




# Source EasyEngien Autocompletion
CMD "source /etc/bash_completion.d/ee_auto.rc"

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
