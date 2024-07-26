FROM php:8.2.21-fpm
RUN apt-get update && apt-get install -y \
    zip \
    unzip \
    libzip-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd \
    && docker-php-ext-install zip pdo pdo_mysql \
    && docker-php-ext-install zip\
    &&pecl install redis \
    && docker-php-ext-enable redis
COPY --from=composer /usr/bin/composer /usr/bin/composer