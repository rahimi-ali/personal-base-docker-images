FROM php:8.5-alpine

LABEL org.opencontainers.image.authors="Ali Rahimi"
LABEL org.opencontainers.image.title="PHP 8.5 with bunch of extensions and MySQL based on Alpine"
LABEL org.opencontainers.image.description="PHP 8.5 + Composer + install-php-extensions + (BCMath, ZIP, Redis, GD, PDO_MYSQL, DOM, fileinfo, INTL)"

RUN apk add --update nano curl bash git nodejs npm

COPY --from=mlocati/php-extension-installer:2.10 /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2.9 /usr/bin/composer /usr/local/bin/composer

RUN install-php-extensions bcmath zip redis gd pdo_mysql dom fileinfo intl exif soap