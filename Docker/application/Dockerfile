FROM php:8.1-fpm
RUN apt-get update && \
    apt-get install -y \
        git \
        unzip \
        libicu-dev \
        libzip-dev \
        libonig-dev \
        && \
    docker-php-ext-install \
        intl \
        pdo_mysql \
        zip \
        && \
    pecl install \
        apcu \
        && \
    docker-php-ext-enable \
        apcu

# curl
RUN apt-get install -y curl
# Install Composer 1.10
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=2.5.4

# Install NodeJS V-18
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -
RUN apt-get install -y nodejs


# Set the path to Node.js
ENV PATH="/usr/local/bin/node:${PATH}"

WORKDIR /App