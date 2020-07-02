FROM php:7.2-fpm-alpine
RUN apk add libzip-dev oniguruma-dev libpng-dev postgresql-dev
RUN docker-php-ext-install  mysqli zip mbstring gd pdo pdo_mysql pdo_pgsql
RUN curl --silent --show-error https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

