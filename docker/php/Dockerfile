FROM php:fpm

LABEL maintainer="Ilya Shashilov"

# Install xdebug
RUN pecl install xdebug-2.7.0 \
    && docker-php-ext-enable xdebug
COPY ./docker/php/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

# Install composer
COPY ./docker/php/composer-installer.sh /usr/local/bin/composer-installer
RUN chmod +x /usr/local/bin/composer-installer \
    && composer-installer \
    && mv composer.phar /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer \
    && composer --version

#install git
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git zip

COPY ./docker/php/run-app.sh /usr/local/bin/run-app

#RUN chown -R www-data:www-data /srv/app

WORKDIR /srv/app/

CMD ["/usr/local/bin/run-app"]
