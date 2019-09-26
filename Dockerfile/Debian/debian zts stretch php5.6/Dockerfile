FROM php:5.6-zts-stretch
LABEL Maintainer="qw" \
      Description="gRPC with Linux."

# Install packages
RUN apt-get update && apt-get install -y -q \
    autoconf \
    automake \
    curl \
    git \
    zlib1g-dev \
    libtool \
    nginx \
    rake \
    vim \
    wget 

###install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
###Install grpc and PHPunit
RUN wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
         chmod +x phpunit  && \
         mv phpunit /usr/bin
#install protoc
RUN mkdir -p /tmp/protoc && \
    curl -L https://github.com/google/protobuf/releases/download/v3.2.0/protoc-3.2.0-linux-x86_64.zip > /tmp/protoc/protoc.zip && \
    cd /tmp/protoc && \
    unzip protoc.zip && \
    cp /tmp/protoc/bin/protoc /usr/local/bin






