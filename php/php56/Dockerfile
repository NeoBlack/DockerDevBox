FROM php:5.6-fpm

MAINTAINER Frank Nägler <frank.naegler@typo3.com>

# Fix docker-php-ext-install script error
RUN sed -i 's/docker-php-\(ext-$ext.ini\)/\1/' /usr/local/bin/docker-php-ext-install

# Install other needed extensions
RUN apt-get update && \
   apt-get install -y mysql-client && \
   apt-get install -y ssh && \
   apt-get install -y rsync && \
   apt-get install -y ssmtp && \
   apt-get install -y libfreetype6-dev libjpeg62-turbo-dev && \
   docker-php-ext-install mysqli && \
   docker-php-ext-install mbstring && \
   docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/  &&  \
   docker-php-ext-install gd

# Install Composer for Laravel
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

COPY ./php.ini /usr/local/etc/php/php.ini
COPY ./ssmtp.conf /etc/ssmtp/ssmtp.conf

WORKDIR /var/www/html