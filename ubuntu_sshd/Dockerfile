FROM ubuntu:14.04
MAINTAINER hejingqi@zj-inv.cn
RUN apt-get install -y apt-transport-https
COPY sources.list /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y openssh-server supervisor vim iputils-ping net-tools lrzsz
RUN mkdir -p /var/run/sshd
COPY sshd_config /etc/ssh/sshd_config
RUN mkdir -p /var/log/supervisor
RUN echo "root:zjht4321"|chpasswd
COPY supervisord.conf /etc/supervisor/supervisord.conf
EXPOSE 22
COPY Shanghai /etc/localtime
RUN echo "Asia/Shanghai" > /etc/timezone
ENV LANG C.UTF-8
RUN echo "export LANG=C.UTF-8" >> /etc/profile
CMD /usr/bin/supervisord -c /etc/supervisor/supervisord.conf
