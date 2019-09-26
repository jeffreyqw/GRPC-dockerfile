From php:7.2-fpm-stretch
LABEL Maintainer="qw" \
      Description="gRPC with PHP-FPM Debian Gun Linux."

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y \
         automake \
         build-essential \
         git \
         libtool \
         vim \
         libz-dev \
         wget

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
         chmod +x phpunit  && \
         mv phpunit /usr/bin && \
###install gRPC
         pecl install grpc && \
         pecl install protobuf && \
         echo extension=grpc.so > /usr/local/etc/php/conf.d/grpc.ini && \
         echo extension=protobuf.so > /usr/local/etc/php/conf.d/protobuf.ini



CMD ["php-fpm"]
