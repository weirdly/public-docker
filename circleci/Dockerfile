FROM circleci/php:7.2-fpm-node-browsers

USER root

RUN ["/bin/bash", "mkdir", "-p", "/usr/share/man/man{1,7}"]
RUN apt-get update || apt-get update
RUN apt-get install postgresql-client-9.6 libpq-dev acl
RUN docker-php-ext-install pdo pdo_mysql pdo_pgsql pcntl
RUN pecl install apcu && docker-php-ext-enable apcu
RUN rm -rf /var/www/*
RUN chown circleci /var/www

USER circleci