FROM php:8.0-apache-bullseye
WORKDIR /var/www/html/

RUN apt-get update && apt-get install -y \
      apt-utils \
      libfreetype6-dev \
      libjpeg62-turbo-dev \
      libpq-dev \
      libpng-dev \
      libzip-dev \
      zip unzip \
      git iputils-ping \
      wget \
      build-essential \
      libncursesw5-dev \
      libssl-dev \
      libsqlite3-dev \
      tk-dev \
      libgdbm-dev \
      libc6-dev \
      libbz2-dev \
      libffi-dev \
      libicu-dev \
      libc-client-dev \
      libkrb5-dev \
      zlib1g-dev && \
      pecl install apcu && \
      docker-php-ext-enable apcu &&\
      docker-php-ext-install mysqli && \
      docker-php-ext-enable mysqli && \
      docker-php-ext-install bcmath && \
      docker-php-ext-install gd && \
      docker-php-ext-install zip && \
      docker-php-ext-install intl && \
      docker-php-ext-configure imap --with-kerberos --with-imap-ssl && \
      docker-php-ext-install imap && \
      docker-php-ext-configure opcache --enable-opcache && \
      apt-get clean && \
      rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
      a2enmod rewrite && \
      a2enmod headers

COPY ./conf/php.ini /usr/local/etc/php/php.ini
COPY ./conf/opcache.ini /usr/local/etc/php/conf.d/opcache.ini
COPY ./conf/000-default.conf /etc/apache2/sites-available/000-default.conf
