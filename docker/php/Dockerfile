FROM php:8-fpm

RUN apt-get update  \
    && apt-get install -y \
      curl; \

    docker-php-ext-configure shmop --enable-shmop; \

    docker-php-ext-install -j "$(nproc)" \
      shmop;

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /app

CMD ["php-fpm"]
