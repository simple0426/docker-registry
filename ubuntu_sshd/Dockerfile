FROM ubuntu:14.04
LABEL maintainer hejingqi@zj-inv.cn
ENV LANG C.UTF-8
RUN echo 'deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse\n\
	deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse\n\
	deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse\n\
	deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse\n\
	deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse\n\
	deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse\n\
	deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse\n\
	deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse\n'\
	> /etc/apt/sources.list && \
	rm -rf /etc/apt/sources.list.d/* && \
	apt-get update && \
	apt-get install -y openssh-server vim iputils-ping net-tools lrzsz && \
	mkdir -p /var/run/sshd && \
	sed -i '/^PermitRootLogin/s/without-password/yes/' /etc/ssh/sshd_config && \
	sed -i '/^#PasswordAuthentication/s/#//' /etc/ssh/sshd_config && \
	echo "root:zjht4321"|chpasswd && \
	ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
	rm -rf /var/cache/apt/*
EXPOSE 22
CMD /usr/sbin/sshd -D
