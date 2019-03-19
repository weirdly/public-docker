FROM circleci/php:7.2-fpm-node-browsers

RUN ["/bin/bash", "sudo", "mkdir", "-p", "/usr/share/man/man{1,7}"]
RUN sudo apt-get update || sudo apt-get update
RUN sudo apt-get install postgresql-client-9.6 libpq-dev acl
RUN sudo docker-php-ext-install pdo pdo_mysql pdo_pgsql pcntl
RUN sudo pecl install apcu && sudo docker-php-ext-enable apcu
RUN sudo rm -rf /var/www/*
RUN sudo chown circleci /var/www
