FROM alpine:3.18.2

RUN apk update --no-cache && apk upgrade --no-cache && apk add --no-cache \
    php82 \
    php82-fpm \
    nginx \
    supervisor \
    curl

# supervisord
RUN mkdir -p /etc/supervisor.d
RUN mv /etc/supervisord.conf /etc/supervisord.conf_backup
COPY supervisord.conf /etc/supervisord.conf

# php-fpm
COPY supervisor.d/php-fpm-supervisor.conf /etc/supervisor.d/php-fpm.conf

# nginx
COPY supervisor.d/nginx-supervisor.conf /etc/supervisor.d/nginx.conf
RUN mv /etc/nginx/http.d/default.conf /etc/nginx/http.d/default.conf_backup
COPY nginx/default.conf /etc/nginx/http.d/default.conf

COPY index.php /var/www/localhost/htdocs

EXPOSE 80

#ENTRYPOINT [ "/bin/ash" ]
ENTRYPOINT ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]
