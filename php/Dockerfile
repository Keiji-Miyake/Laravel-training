FROM php:7.4-fpm

RUN mv $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini && \
    sed -i -e "s|;session.save_path = "/tmp"|session.save_path = "/tmp" |" /usr/local/etc/php/php.ini && \
    sed -i -e "s|;extension=php_openssl.dll|extension=php_openssl.dll |" /usr/local/etc/php/php.ini && \
    apt-get update && \
    apt-get install -y git \
        libonig-dev \
        zlib1g-dev \
        libzip-dev \
        mariadb-client \
        unzip \
        locales \
        openssl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    git clone https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis && \
    docker-php-ext-install pdo_mysql session json redis && \
    pecl install mailparse  && \
    pecl install xdebug && \
    docker-php-ext-enable mailparse xdebug

COPY ./xdebug.ini $PHP_INI_DIR/conf.d/
RUN chown -R www-data:www-data /var/www/
