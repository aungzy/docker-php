FROM php:5.6-apache

RUN curl -sS https://getcomposer.org/installer | php; \
  mv composer.phar /usr/local/bin/composer; \
  curl -sL https://deb.nodesource.com/setup_4.x | bash -; \
  apt-get install -y git nodejs zlib1g-dev libnotify-bin vim; \
  npm install -g bower gulp; \
  docker-php-ext-install mbstring; \
  docker-php-ext-install zip; \
  a2enmod rewrite
