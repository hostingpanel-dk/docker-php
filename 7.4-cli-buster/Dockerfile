FROM php:7.4-cli

RUN apt-get update && apt-get install -y \
    libvips-dev \
    libcurl3-openssl-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    zlib1g-dev \
    libxml2-dev \
    libzip-dev \
    libonig-dev \
    graphviz

# PHP options bcmath bz2 calendar ctype curl dba dom enchant exif ffi fileinfo filter ftp
# gd gettext gmp hash iconv imap intl json ldap mbstring mysqli oci8 odbc opcache pcntl
# pdo pdo_dblib pdo_firebird pdo_mysql pdo_oci pdo_odbc pdo_pgsql pdo_sqlite pgsql phar posix
# pspell readline reflection session shmop simplexml snmp soap sockets sodium spl standard
# sysvmsg sysvsem sysvshm tidy tokenizer xml xmlreader xmlrpc xmlwriter xsl zend_test zip
RUN docker-php-ext-install bcmath curl json pcntl pdo pdo_mysql zip sockets soap gd exif xml
RUN pecl install redis
RUN pecl install vips
RUN pecl install swoole
RUN docker-php-ext-enable redis vips swoole
RUN docker-php-source delete
RUN apt-get clean
