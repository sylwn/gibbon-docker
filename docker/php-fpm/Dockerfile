# To change this license header, choose License Headers in Project Properties.
# To change this template file, choose Tools | Templates
# and open the template in the editor.
FROM php:7.3-fpm
ARG TIMEZONE
ARG LOCALES

MAINTAINER Laurent BRELEUR <laurent.breleur@gmail.com>

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libpng-dev \
    libzip-dev \
    locales

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Set timezone
RUN ln -snf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && echo ${TIMEZONE} > /etc/timezone
RUN printf '[PHP]\ndate.timezone = "%s"\n', ${TIMEZONE} > /usr/local/etc/php/conf.d/tzone.ini
RUN "date"

RUN echo ${LOCALES}
COPY ./conf/locale.gen /etc/locale.gen
RUN sed -i -e "s/__LOCALES__/${LOCALES}/g" /etc/locale.gen
RUN sed -i -e "s/, /\n/g" /etc/locale.gen
RUN /usr/sbin/locale-gen

# Type docker-php-ext-install to see available extensions
RUN docker-php-ext-install pdo pdo_mysql gettext gd zip

WORKDIR /var/www/gibbon

EXPOSE 80
EXPOSE 443
