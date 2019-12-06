FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
    libc-client-dev \
    libkrb5-dev \
    libxml2-dev \
    libpq-dev \
    git \
    zip \
    && docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    && docker-php-ext-install imap soap pdo pdo_pgsql \
    && apt-get clean -y && apt-get autoclean -y && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer /usr/bin/composer /usr/bin/composer
