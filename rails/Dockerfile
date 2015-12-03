FROM centos

MAINTAINER yamamoto <yamamoto@smile-works.co.jp>

RUN yum -y update
RUN yum -y upgrade
RUN yum -y groups mark convert
RUN yum -y groupinstall "Development Tools" | true
RUN yum -y install vim-enhanced | true
RUN yum -y install wget
RUN yum install -y openssl-devel readline-devel zlib-devel | true
RUN yum -y install epel-release
RUN yum -y --enablerepo=epel install nodejs
RUN rpm -ivh http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm
RUN yum --enablerepo=mysql56-community -y install mysql-community-devel

RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
RUN git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
RUN ./root/.rbenv/plugins/ruby-build/install.sh
ENV PATH /root/.rbenv/bin:$PATH
RUN echo 'export PATH=/root/.rbenv/bin:$PATH' >> /root/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> /root/.bashrc

ENV CONFIGURE_OPTS --disable-install-doc
RUN rbenv install 2.2.3
RUN rbenv global 2.2.3

RUN echo 'gem: --no-rdoc --no-ri' >> /.gemrc

RUN bash -l -c 'gem install bundler' | true

RUN mkdir /root/repos
CMD cd /root/repos


EXPOSE 3000
