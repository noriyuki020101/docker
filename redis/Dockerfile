FROM centos

MAINTAINER noriyuki020101 <noriyuki020101@gmail.com>

RUN yum -y update
RUN yum -y install wget
RUN wget -r --no-parent -A 'epel-release-*.rpm' http://dl.fedoraproject.org/pub/epel/7/x86_64/e/
RUN rpm -Uvh dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-*.rpm
RUN yum -y install redis

EXPOSE 3306
