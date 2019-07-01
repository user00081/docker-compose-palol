ARG CODE_VERSION=centos7
ARG PHP_VERSION=php73
FROM centos:${CODE_VERSION}
MAINTAINER Luca Palo <palo@programmer.net>

RUN yum repolist

RUN yum install -y ntp
RUN ntpdate time.nist.gov
RUN timedatectl set-timezone Europe/Zurich

RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm

# yum-utils enables or disables repositories as well as packages without any manual configuration
RUN yum install -y yum-utils

# Choose which version of PHP should be installed (uncomment only one of the following versions)
#yum-config-manager --enable remi-php70
#yum-config-manager --enable remi-php71
#yum-config-manager --enable remi-php72
RUN yum-config-manager --enable remi-php73

# Install PHP modules
RUN yum install -y php php-mcrypt php-cli php-gd php-curl php-mysql php-ldap php-zip php-fileinfo php-vlucas-phpdotenv
RUN yum install -y php php5-cli php5-dev php5-fpm php5-cgi php5-mysql php5-xmlrpc php5-curl php5-gd php-apc php-pear php5-imap php5-mcrypt php5-pspell

# Database access abstraction module for PHP applications
#yum install -y php70-php-pdo.x86_64
#yum install -y php71-php-pdo.x86_64
#yum install -y php72-php-pdo.x86_64
RUN yum install -y php73-php-pdo.x86_64
#yum install -y php74-php-pdo.x86_64

EXPOSE 80:tcp

VOLUME /var/www/html
WORKDIR /var/www/html
RUN "Terminal set in:"
RUN pwd
