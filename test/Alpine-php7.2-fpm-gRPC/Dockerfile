FROM php:7.2-fpm-alpine3.10
LABEL Maintainer="qw" \
      Description="gRPC with PHP-FPM Alpine Linux."

# Install packages
RUN apk update && apk upgrade && apk --no-cache add \
    autoconf \
    automake \
    build-base \
    curl \
    git \
    libtool \
    vim \
    wget \
    zlib-dev

###install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
###Install grpc and PHPunit
RUN wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
         chmod +x phpunit  && \
         mv phpunit /usr/bin && \
###install gRPC & protobuf
          pecl install grpc && \
          pecl install protobuf


STOPSIGNAL SIGQUIT
EXPOSE 9000
CMD ["php-fpm"]
