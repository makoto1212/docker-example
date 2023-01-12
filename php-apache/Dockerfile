FROM php:7.3.29-apache-buster

RUN apt-get update && apt-get install -y \
    vim

COPY ./index.php /var/www/html

WORKDIR /var/www/html
