FROM doanhpv/composer

MAINTAINER doanhpv

ENV PHPUNIT_VERSION=6.0
ENV XDEBUG_VERSION=2.6.0

ENV PHPIZE_DEPS \
    file \
    re2c \
    autoconf \
    make \
    zlib \
    zlib-dev \
    g++

# Install autoconfig
RUN apk add --update --no-cache --virtual .build-deps ${PHPIZE_DEPS}

# Install some extensions
RUN docker-php-ext-install pdo_mysql

# Install phpunit
RUN composer global require phpunit/phpunit ~$PHPUNIT_VERSION --no-progress --no-scripts --no-interaction

# Run xdebug installation.
RUN pecl install -o -f xdebug \
    && rm -rf /tmp/pear \
    && echo "zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-20160303/xdebug.so" > /usr/local/etc/php/conf.d/xdebug.ini

RUN apk del --purge .build-deps

WORKDIR /var/www/laravel

ENTRYPOINT ["/root/.composer/vendor/bin/phpunit"]

CMD ["--help"]
