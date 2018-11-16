FROM ubuntu
ENV password "pass"
ENV rootPassword "pass"
ENV user "user"

##Install basic
RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y curl
RUN apt-get install -y sudo
RUN apt-get install -y gnupg2
RUN apt-get install -y net-tools
RUN apt-get install -y nano
RUN apt-get install -y ssh
RUN apt-get install -y iputils-ping 
RUN apt-get install -y sudo

## Setup user
RUN useradd -ms /bin/bash ${user}
RUN echo root:${password} | chpasswd
RUN echo ${user}:${password} | chpasswd

RUN sudo apt-get install -y mysql-server mysql-client

COPY Config /etc/mysql

RUN sudo service mysql restart