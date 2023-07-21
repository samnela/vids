FROM php:8.2-cli

WORKDIR /app

ENV COMPOSER_ALLOW_SUPERUSER=1
ENV PATH="${PATH}:/root/.composer/vendor/bin"

COPY --from=composer/composer:2-bin /composer /usr/bin/composer
COPY . .

RUN apt update && apt install -y git libzip-dev unzip
RUN docker-php-ext-install zip 
RUN pecl install pcov ;\
    docker-php-ext-enable pcov
