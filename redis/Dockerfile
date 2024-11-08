FROM redis:7.2

RUN mkdir -p /usr/local/etc/redis
COPY ./redis.conf /usr/local/etc/redis

ENTRYPOINT ["redis-server", "/usr/local/etc/redis/redis.conf"]