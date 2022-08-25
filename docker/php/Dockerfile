FROM php:8.1-apache

RUN echo "Europe/Berlin" > /etc/timezone && dpkg-reconfigure -f noninteractive tzdata

RUN apt-get update && apt-get install -y ca-certificates gnupg
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash -

RUN apt-get update && apt-get upgrade -y && apt-get install -y git nodejs zip unzip libzip-dev libicu-dev nano


RUN /usr/sbin/a2enmod rewrite && /usr/sbin/a2enmod headers && /usr/sbin/a2enmod expires

RUN cp /usr/local/etc/php/php.ini-production /usr/local/etc/php/php.ini
RUN pear config-set php_ini /usr/local/etc/php/php.ini

RUN docker-php-ext-install \
    zip \
    intl \
    pdo \
    pdo_mysql

RUN pecl install mongodb && docker-php-ext-enable mongodb
RUN pecl install redis && docker-php-ext-enable redis

#RUN pecl install xdebug && docker-php-ext-enable xdebug
#RUN echo 'zend_extension=xdebug' >> /usr/local/etc/php/php.ini
#RUN echo 'xdebug.mode=develop,debug' >> /usr/local/etc/php/php.ini
#RUN echo 'xdebug.client_host=host.docker.internal' >> /usr/local/etc/php/php.ini
#RUN echo 'xdebug.start_with_request=yes' >> /usr/local/etc/php/php.ini
#RUN echo 'session.save_path = "/tmp"' >> /usr/local/etc/php/php.ini

# COPY --from=composer /usr/bin/composer /usr/local/bin/composer

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash
RUN apt install symfony-cli

COPY . /var/www/html

WORKDIR /var/www/html

