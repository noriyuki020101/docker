FROM centos
MAINTAINER yamamoto <yamamoto@smile-works.co.jp>
RUN yum -y update
RUN yum -y upgrade
RUN yum -y install epel-release
RUN yum -y --enablerepo=epel install nginx
EXPOSE 80
