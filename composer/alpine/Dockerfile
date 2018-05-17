FROM php:7.1-alpine

MAINTAINER doanhpv

RUN apk --no-cache --update add curl openssl

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_VERSION 1.6.3

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=${COMPOSER_VERSION} && \
    chmod +x /usr/local/bin/composer && \
    apk del curl openssl && \
    rm -rf /var/cache/apk/*

# Command
CMD ["/usr/local/bin/composer", "--help"]
