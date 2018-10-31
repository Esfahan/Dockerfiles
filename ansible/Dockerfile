FROM centos:7

RUN yum update -y

# ansible
RUN yum clean all && \
    yum -y install epel-release && \
    yum -y install PyYAML \
    python-jinja2 \
    python-httplib2 \
    python-keyczar \
    python-paramiko \
    python-setuptools \
    python-pip \
    ansible
