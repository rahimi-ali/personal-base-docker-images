FROM php:8.4-alpine

LABEL authors="Ali Rahimi"

COPY --from=ghcr.io/mlocati/php-extension-installer:2.7 /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2.8 /usr/bin/composer /usr/local/bin/composer

RUN install-php-extensions bcmath zip redis swoole pdo_mysql

RUN apk add --update nano