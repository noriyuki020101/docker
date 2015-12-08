FROM centos
MAINTAINER yamamoto <yamamoto@smile-works.co.jp>
RUN yum -y update
RUN yum -y upgrade
RUN yum -y groups mark convert
RUN yum -y groupinstall "Development Tools" | true
RUN yum -y install vim-enhanced
RUN yum -y install http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
RUN yum -y install --enablerepo=nginx nginx
EXPOSE 80
