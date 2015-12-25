FROM centos
MAINTAINER yamamoto <yamamoto@smile-works.co.jp>
RUN yum -y update
RUN yum -y upgrade
RUN yum -y groups mark convert
RUN yum -y groupinstall "Development Tools" | true
RUN yum -y install vim-enhanced
RUN yum -y install readline-devel pcre-devel openssl-devel
RUN mkdir /opt/src
RUN cd /opt/src && curl -O https://openresty.org/download/ngx_openresty-1.9.3.2.tar.gz && tar xvfz ngx_openresty-1.9.3.2.tar.gz
RUN cd /opt/src/ngx_openresty-1.9.3.2 && /opt/src/ngx_openresty-1.9.3.2/configure --prefix=/opt/openresty/1.9.3.2 --with-luajit && make && make install
ADD nginx.service /lib/systemd/system/nginx.service
RUN systemctl enable nginx
EXPOSE 80
