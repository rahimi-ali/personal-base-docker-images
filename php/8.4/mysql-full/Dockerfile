FROM php:8.4-alpine

LABEL org.opencontainers.image.authors="Ali Rahimi"
LABEL org.opencontainers.image.title="PHP 8.4 with bunch of extensions and MySQL based on Alpine"
LABEL org.opencontainers.image.description="PHP 8.4 + Composer + install-php-extensions + (BCMath, ZIP, Redis, GD, PDO_MYSQL, DOM, fileinfo, INTL)"

COPY --from=ghcr.io/mlocati/php-extension-installer:2.7 /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2.8 /usr/bin/composer /usr/local/bin/composer

RUN install-php-extensions bcmath zip redis gd pdo_mysql dom fileinfo intl

RUN apk add --update nano