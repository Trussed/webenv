FROM php:7-fpm-alpine3.10

RUN apk update \
    && apk add libpng-dev \ 
    && apk add --no-cache $PHPIZE_DEPS \
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install gd

# Install supervisor
RUN apk update \
    && apk add supervisor

COPY supervisord.conf /etc/supervisord.conf

ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c",  "/etc/supervisord.conf"]

# Define working directory
WORKDIR /etc/supervisor/conf.d