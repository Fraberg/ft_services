FROM wordpress:php7.4-fpm-alpine

RUN apk -f upgrade && apk -f update
RUN apk -f add nginx mysql-client mysql-server

COPY entrypoint.sh /entrypoint.sh
COPY nginx.conf /etc/nginx/nginx.conf
COPY wordpress.sql /wordpress.sql
RUN chmod 777 /wordpress.sql
COPY wp-config.php /wp-config.php

EXPOSE 5050
ENTRYPOINT ["sh", "/entrypoint.sh"]