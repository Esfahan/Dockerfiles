From centos:7

ARG GO_VER=1.11

RUN yum update -y

# Golang
WORKDIR /usr/local/src
RUN yum install -y git
RUN curl -O https://dl.google.com/go/go${GO_VER}.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go${GO_VER}.linux-amd64.tar.gz

ENV GOPATH=/code
ENV PATH=$PATH:$GOPATH/bin
ENV PATH=$PATH:/usr/local/go/bin

# PhantomJS
RUN yum install -y epel-release
RUN rpm -ivh http://repo.okay.com.mx/centos/6/x86_64/release/okay-release-1-1.noarch.rpm
RUN yum install -y phantomjs.x86_64
