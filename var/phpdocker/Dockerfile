FROM phpdockerio/php73-fpm:latest

# Create working folder if it doesn't already exists
RUN mkdir -p /var/www/html
WORKDIR "/var/www/html"
RUN echo "ServerName localhost" >> /etc/httpd/conf/httpd.conf
COPY . /var/www/html/

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install  php7.3-mysql php-redis php7.3-sqlite3 php-xdebug php7.3-gd php7.3-xmlrpc php-yaml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install git
RUN apt-get update \
    && apt-get -y install git \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');    \
        \$sig = file_get_contents('https://composer.github.io/installer.sig');      \
        if (trim(\$sig) === hash_file('SHA384', 'composer-setup.php')) exit(0);     \
        echo 'ERROR: Invalid installer signature' . PHP_EOL;                        \
        unlink('composer-setup.php');                                               \
        exit(1);"                                                                   \
     && php composer-setup.php -- --filename=composer --install-dir=/usr/local/bin  \
     && rm composer-setup.php

EXPOSE 80
