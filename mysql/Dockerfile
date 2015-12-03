FROM centos

MAINTAINER yamamoto <yamamoto@smile-works.co.jp>

RUN yum -y update
RUN rpm -ivh http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm
RUN yum --enablerepo=mysql56-community -y install mysql-community-server

EXPOSE 3306
