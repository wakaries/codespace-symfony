FROM php:8.1-apache

RUN apt update && apt upgrade -y


RUN docker-php-ext-install \
    zip \
    intl \
    pdo

RUN git config --global user.name "Jose J. Matarin"
RUN git config --global user.password "jmatarin@wakari.es"

COPY . /var/www/html

WORKDIR /var/www/html

