FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
    libc-client-dev \
    libkrb5-dev \
    libxml2-dev \
    libpq-dev \
    libssl-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libzip-dev \
    zlib1g-dev \
    libicu-dev \
    g++ \
    git \
    zip \
    && PHP_OPENSSL=yes docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    && docker-php-ext-configure gd --with-jpeg \
    && docker-php-ext-configure intl \
    && docker-php-ext-install imap soap pdo pdo_pgsql pdo_mysql gd zip intl exif opcache bcmath sockets \
    && apt-get clean -y && apt-get autoclean -y && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer /usr/bin/composer /usr/bin/composer
