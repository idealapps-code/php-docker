FROM nginx:1.26

RUN apt update && apt -y install certbot python3-certbot-nginx

COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./default.conf /etc/nginx/conf.d/default.conf