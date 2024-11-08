FROM ubuntu:24.04

COPY ./ /var/www/default/
RUN rm -f /var/www/default/Dockerfile

RUN chown -R www-data:www-data /var/www
RUN find /var/www -type f -exec 644 {} \;
RUN find /var/www -type d -exec 755 {} \;