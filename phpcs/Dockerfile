FROM composer:latest

ENV PHPCS_VERSION=3.5.8

RUN apk --no-cache --update add git

# Install phpcs
RUN composer global require squizlabs/php_codesniffer=$PHPCS_VERSION

# Install Framgia's Standard for phpcs
RUN git clone https://github.com/wataridori/framgia-php-codesniffer.git ~/.composer/vendor/squizlabs/php_codesniffer/src/Standards/Framgia
RUN ln -s /root/.composer/vendor/bin/phpcs /usr/local/bin/phpcs

WORKDIR /var/www/laravel

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["composer"]