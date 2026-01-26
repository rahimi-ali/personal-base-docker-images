FROM php:8.4-alpine

LABEL org.opencontainers.image.authors="Ali Rahimi"
LABEL org.opencontainers.image.title="PHP 8.4 with Almost all usefull php extensions with Swoole based on Alpine"
LABEL org.opencontainers.image.description="PHP 8.4 + Composer + install-php-extensions + ..."

RUN apk add --update nano curl bash git

COPY --from=ghcr.io/mlocati/php-extension-installer:2.9 /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2.9 /usr/bin/composer /usr/local/bin/composer

RUN install-php-extensions bcmath zip redis gd pdo_mysql pdo_pgsql dom fileinfo intl exif pcntl swoole brotli bz2 csv imagick intl mongodb parallel sqlite3
