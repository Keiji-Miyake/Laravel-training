FROM php:7.4-apache
ENV DEBIAN_FRONTEND noninteractive
ENV PHPREDIS_VERSION php7
RUN apt-get update && apt-get install -y \
    git vim \
    mariadb-client \
    libzip-dev openssl \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    && docker-php-ext-install pdo_mysql mysqli zip bcmath \
        -j$(nproc) iconv gd \
    && docker-php-source extract 
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer \
    && chown -R www-data:www-data /var/www \
    && a2enmod rewrite \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug
