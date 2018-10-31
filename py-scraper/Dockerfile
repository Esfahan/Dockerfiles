From centos:7

ARG PY_VER=3.7.0

RUN yum update -y

# Dpendencies
RUN yum -y install zlib \
                   tk-devel \
                   tcl-devel \
                   ncurses-devel \
                   gdbm-devel \
                   db4-devel \
                   readline-devel \
                   zlib-devel \
                   bzip2-devel \
                   sqlite-devel \
                   openssl-devel \
                   libXext.x86_64 \
                   libSM.x86_64 \
                   libXrender.x86_64 \
                   gcc \
                   gcc-c++ \
                   libffi-devel \
                   python-devel \
                   patch \
                   bzip2 \
                   make

# python
RUN curl -O https://www.python.org/ftp/python/${PY_VER}/Python-${PY_VER}.tgz
RUN tar zxfv Python-${PY_VER}.tgz

WORKDIR Python-${PY_VER}
RUN ./configure --enable-unicode=ucs4 --prefix=/usr/local
RUN make
RUN make install

# pip
RUN curl -O https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py

# symlink for python3.x
RUN  PY_MVER=$(echo ${PY_VER} | sed s/\.[0-9,]\.[0-9,]*$//g); \
echo ${PY_MVER}; \
if [ "${PY_MVER}" = "3" ]; then \
      ln -s /usr/local/bin/python3 /usr/local/bin/python; \
      ln -s /usr/local/bin/pip3 /usr/local/bin/pip; \
fi

# PhantomJS
RUN yum install -y epel-release
RUN rpm -ivh http://repo.okay.com.mx/centos/6/x86_64/release/okay-release-1-1.noarch.rpm
RUN yum install -y phantomjs.x86_64
