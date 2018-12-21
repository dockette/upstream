FROM php:7.0-alpine

MAINTAINER Milan Sulc <sulcmil@gmail.com>

# PHP
ENV PHP_CONF_DIR=/usr/local/etc/php/conf.d
ENV TZ=Europe/Prague

RUN apk update && \
    # DEPENDENCIES #############################################################
    apk add curl && \
    # DEPENDENCIES #############################################################
    docker-php-ext-install bcmath && \
    docker-php-ext-install calendar && \
    docker-php-ext-install cgi && \
    docker-php-ext-install cli && \
    docker-php-ext-install common && \
    docker-php-ext-install pdo && \
    docker-php-ext-install pdo_mysql && \
    docker-php-ext-install xml && \
    # COMPOSER #################################################################
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer global require "hirak/prestissimo:^0.3" && \
    # CLEAN UP #################################################################
    apk del curl && \
    rm -rf /var/cache/apk/*

# FILES (it overrides originals)
ADD conf.d/custom.ini ${PHP_CONF_DIR}/999-custom.ini

# WORKDIR
WORKDIR /srv

# COMMAND
CMD ["php"]
