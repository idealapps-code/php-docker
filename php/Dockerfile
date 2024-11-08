FROM php:8.3-fpm AS production
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN install-php-extensions opcache redis gd
COPY ./www.conf /usr/local/etc/php-fpm.d/
COPY ./php.ini-production /usr/local/etc/php/php.ini

FROM php:8.3-fpm AS development
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN install-php-extensions opcache redis gd
COPY ./www.conf /usr/local/etc/php-fpm.d/
COPY ./php.ini-development /usr/local/etc/php/php.ini