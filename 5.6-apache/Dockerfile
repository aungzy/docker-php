FROM php:5.6-apache

RUN curl -sS https://getcomposer.org/installer | php; \
  mv composer.phar /usr/local/bin/composer; \
  curl -sL https://deb.nodesource.com/setup_4.x | bash -; \
  apt-get install -y git nodejs zlib1g-dev libnotify-bin libpq-dev postgresql-client mysql-client vim; \
  npm install -g bower gulp; \
  docker-php-ext-install mbstring zip mysql pdo_mysql pgsql pdo_pgsql gd; \
  a2enmod rewrite
