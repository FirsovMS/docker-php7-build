# use stable 7.2 php-fpm
FROM php:7.2-fpm

# Install dependecies and update ubuntu distro
RUN apt-get update && apt-get install -y \
        curl \
        wget \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt mbstring mysqli pdo_mysql zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
    
# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Add your's custom php.ini file
ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini

# set up project directory
WORKDIR /var/www

# Run container
CMD ["php-fpm"]