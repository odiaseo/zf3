FROM php:7.0-fpm
RUN apt-get update && apt-get install -y \
        apt-utils \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        git zlib1g-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt pdo_mysql zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && curl -sS https://getcomposer.org/installer \
      | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www