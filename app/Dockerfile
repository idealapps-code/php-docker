FROM ubuntu:24.04

COPY ./data/ /var/www/default/

RUN chown -R www-data:www-data /var/www
RUN find /var/www -type f -exec 644 {} \;
RUN find /var/www -type d -exec 755 {} \;