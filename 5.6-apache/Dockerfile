FROM php:5.6-apache

RUN apt-get update -y; apt-get upgrade -y; \
    curl -sL https://deb.nodesource.com/setup_4.x | bash -; \
    apt-get install -y libfreetype6 libjpeg62-turbo libmcrypt4 libpng12-0 sendmail --no-install-recommends; \
    BUILD_DEPS=" libfreetype6-dev libjpeg-dev libldap2-dev libmcrypt-dev libpng12-dev zlib1g-dev libpq-dev "; \
    apt-get install -y -y $BUILD_DEPS --no-install-recommends; \
    apt-get install -y git nodejs libnotify-bin postgresql-client mysql-client vim --no-install-recommends && rm -rf /var/lib/apt/lists/*; \
    docker-php-ext-install mbstring mcrypt zip mysql mysqli pdo_mysql pgsql pdo_pgsql gd; \
    docker-php-ext-configure gd --enable-gd-native-ttf --with-jpeg-dir=/usr/lib/x86_64-linux-gnu --with-png-dir=/usr/lib/x86_64-linux-gnu --with-freetype-dir=/usr/lib/x86_64-linux-gnu; \
    apt-get purge -y --auto-remove $BUILD_DEPS; \
    cd /usr/src/php; \
    make clean; \
    curl -sS https://getcomposer.org/installer | php; \
    mv composer.phar /usr/local/bin/composer; \
    npm install -g bower gulp; \
    a2enmod rewrite
