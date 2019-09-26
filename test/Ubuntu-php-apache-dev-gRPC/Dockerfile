FROM webdevops/php-apache-dev:ubuntu-18.04
LABEL Maintainer="qw" \
      Description="gRPC with PHP-FPM & apache based on ubuntu Linux."
RUN apt-get update && apt-get install -y \
         autoconf \
         build-essential \
         curl \
         git \
         libtool \
         zlib1g-dev \
         php-dev \
         wget \
         vim 
         
###Install composer and phpunit
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
    chmod +x phpunit && \
    mv phpunit /usr/bin && \
    ###install gRPC
         pecl install grpc && \
         pecl install protobuf && \
         echo extension=grpc.so > /usr/local/etc/php/php.ini-development && \
         echo extension=protobuf.so > /usr/local/etc/php/php.ini-development
