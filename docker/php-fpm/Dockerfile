FROM php:7-fpm-alpine

RUN apk update \
    && apk add libpng-dev \ 
    && apk add --no-cache $PHPIZE_DEPS \
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install gd \ 
    && pecl install xdebug \
    && docker-php-ext-enable xdebug