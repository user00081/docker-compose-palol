ARG CODE_VERSION=centos7
ARG PHP_VERSION=php73
FROM centos:${CODE_VERSION}
MAINTAINER Luca Palo <palo@programmer.net>

RUN yum repolist


EXPOSE 80:tcp

VOLUME /var/www/html
WORKDIR /var/www/html
RUN "Terminal set in:"
RUN pwd
