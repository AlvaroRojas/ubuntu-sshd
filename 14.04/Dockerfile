FROM       ubuntu:14.04
MAINTAINER Aleksandar Diklic "https://github.com/AlvarRojas"

RUN apt-get update

RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd

RUN echo 'root:root' |chpasswd

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22
EXPOSE 9987
EXPOSE 30033
EXPOSE 10011
EXPOSE 8087

CMD    ["/usr/sbin/sshd", "-D"]
