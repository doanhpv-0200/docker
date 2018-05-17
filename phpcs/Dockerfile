FROM doanhpv/composer

MAINTAINER doanhpv

# phpcs version 3.2.3
ENV PHPCS_VERSION=3.2.3

# framgia-php-codesniffer version 0.2.0
ENV FRAMGIA_CODESNIFFER_VERSION=0.2.0

RUN apk --no-cache --update add git

# Install phpcs
RUN composer global require squizlabs/php_codesniffer=$PHPCS_VERSION

# Install Framgia's Standard for phpcs
RUN git clone https://github.com/wataridori/framgia-php-codesniffer.git ~/.composer/vendor/squizlabs/php_codesniffer/src/Standards/Framgia
RUN ln -s /root/.composer/vendor/bin/phpcs /usr/local/bin/phpcs \
    && rm /usr/local/bin/composer \
    && apk del git

WORKDIR /var/www/laravel

ENTRYPOINT ["phpcs"]
CMD ["--version"]
