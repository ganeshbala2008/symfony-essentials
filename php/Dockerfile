FROM php:8.0-fpm AS symfony_php

RUN apt update \
    && apt install -y git \
    && docker-php-ext-install intl opcache pdo pdo_mysql \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

WORKDIR /var/www/app

## Composer configuration
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

## Framework installer - Symfony
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

## Xdebug configuration
FROM symfony_php AS symfony_php_debug

ARG XDEBUG_VERSION=3.1.2
RUN set -eux; \
	pecl install xdebug-$XDEBUG_VERSION; \
	docker-php-ext-enable xdebug;