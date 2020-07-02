FROM php:7.2-apache
EXPOSE 80
WORKDIR /app

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN apt-get update -y && apt-get install -y sendmail libpng-dev zlib1g-dev libzip-dev

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y \
        git \
        zlib1g-dev \
        unzip \
        python 

RUN docker-php-ext-install  mysqli zip mbstring gd

COPY vhost.conf /etc/apache2/sites-available/000-default.conf
RUN chown -R www-data:www-data /app && a2enmod rewrite
