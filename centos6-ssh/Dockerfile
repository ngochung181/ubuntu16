FROM centos:6.8

MAINTAINER vuongtd <vuongtd@runsystem.net>

# Update repo
RUN yum -y update && yum upgrade

# IMPORT GPG KEY
RUN rpm --import http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-6 \
    && rpm --import https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-6 \
    && rpm --import https://dl.iuscommunity.org/pub/ius/IUS-COMMUNITY-GPG-KEY

# Install tools
RUN yum install -y \
        vim \
        python-setuptools-0.6.10-3.el6

# Install supervisor for management services
RUN easy_install \
        'supervisor == 3.3.1' \
        'supervisor-stdout == 0.1.1' && \
    mkdir -p /var/log/supervisor/

# Install services
RUN yum -y install \
        openssh-server

RUN echo "root:toor" | chpasswd

ADD /root / 

CMD ["/usr/bin/supervisord", "--configuration=/etc/supervisord.conf"]
