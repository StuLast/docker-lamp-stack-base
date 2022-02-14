ARG PHP_VERSION

FROM php:${PHP_VERSION}-apache

RUN apt-get update
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www
COPY ./app .
COPY ./app/public ./html