FROM php:5.6-alpine
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
    nginx \
    vim \
    wget \
    zlib-dev

###install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
###Install grpc and PHPunit
RUN wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
         chmod +x phpunit  && \
         mv phpunit /usr/bin





