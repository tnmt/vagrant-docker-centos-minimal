FROM centos:centos6
MAINTAINER tnmt

RUN rpm -ivh http://ftp.riken.jp/Linux/fedora/epel/6/x86_64/epel-release-6-8.noarch.rpm

RUN yum --enablerepo=epel install sudo openssh-server syslog puppet -y

RUN sed -ri "s/^UsePAM yes/#UsePAM yes/" /etc/ssh/sshd_config
RUN sed -ri "s/^#UsePAM no/UsePAM no/" /etc/ssh/sshd_config
RUN sed -ri "s/^.*requiretty/#Defaults requiretty/" /etc/sudoers

RUN echo "root:vagrant" | chpasswd

RUN mkdir -m 700 /root/.ssh
ADD misc/authorized_keys /root/.ssh/authorized_keys
RUN chmod 600 /root/.ssh/authorized_keys && chown -R root. /root/.ssh/

## Init SSHD
RUN /etc/init.d/sshd start
RUN /etc/init.d/sshd stop
