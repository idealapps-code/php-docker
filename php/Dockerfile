FROM php:8.3-fpm AS production
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN docker-php-ext-install opcache pdo_mysql mysqli && install-php-extensions gd redis
ADD --chmod=0755 https://getcomposer.org/download/latest-stable/composer.phar /usr/local/bin/composer
ADD --chmod=0755 https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar /usr/local/bin/wp
RUN apt update
RUN apt install -y git
RUN composer global require laravel/installer
RUN ln -s /root/.composer/vendor/bin/laravel /usr/local/bin/laravel
COPY ./www.conf /usr/local/etc/php-fpm.d/
COPY ./php.ini-production /usr/local/etc/php/php.ini

FROM php:8.3-fpm AS development
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN docker-php-ext-install opcache pdo_mysql mysqli && install-php-extensions gd redis
ADD --chmod=0755 https://getcomposer.org/download/latest-stable/composer.phar /usr/local/bin/composer
ADD --chmod=0755 https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar /usr/local/bin/wp
RUN apt update
RUN apt install -y git
RUN composer global require laravel/installer
RUN ln -s /root/.composer/vendor/bin/laravel /usr/local/bin/laravel
COPY ./www.conf /usr/local/etc/php-fpm.d/
COPY ./php.ini-development /usr/local/etc/php/php.ini