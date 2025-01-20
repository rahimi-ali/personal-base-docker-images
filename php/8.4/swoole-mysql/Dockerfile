FROM php:8.4-alpine

LABEL org.opencontainers.image.authors="Ali Rahimi"
LABEL org.opencontainers.image.title="PHP 8.4 With Swoole and MySQL Based on Alpine"
LABEL org.opencontainers.image.description="PHP 8.4 + Composer + install-php-extensions + (BCMath, ZIP, Redis, Swoole, PDO_MYSQL)"

COPY --from=ghcr.io/mlocati/php-extension-installer:2.7 /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2.8 /usr/bin/composer /usr/local/bin/composer

RUN install-php-extensions bcmath zip redis pcntl swoole pdo_mysql

RUN apk add --update nano