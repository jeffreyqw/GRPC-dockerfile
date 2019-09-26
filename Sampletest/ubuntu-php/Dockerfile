FROM ubuntu:18.04
LABEL Maintainer="qw" \
      Description="gRPC with PHP-FPM & Nginx based on ubuntu Linux."
ENV TZ = US

# Install packages
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y\
    pkg-config unzip build-essential autoconf libtool libgflags-dev \
    libgtest-dev clang libc++-dev \
    php-bz2 \
    php-cli \
    php-dev \
    php-fpm \
    php-gd \
    php-imap \
    php-intl \
    php-json \
    php-mbstring \
    php-mysql \
    php-pear \
    php-pgsql \
    php-sqlite3 \
    php-soap \
    php-tidy \
    php-xmlrpc \
    php-xml \
    libz-dev \
    wget \
    git \
    vim \
    libtool \
    curl \
    g++ \
    autogen \
    make

# install nodejs 
# RUN curl -sL https://deb.nodesource.com/setup_6.x | bash - && apt-get install -y nodejs

# install composer 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#install grpc and PHPunit 
RUN git clone https://github.com/grpc/grpc.git && \
    git clone https://github.com/google/protobuf.git && \
    wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
    chmod +x phpunit  && \
    mv phpunit /usr/bin  && \

# Setup document root
mkdir -p /var/www/html

# Configure nginx
# COPY nginx.conf /etc/nginx/nginx.conf

# Configure PHP-FPM
# COPY php-fpm.conf /etc/php/7.2/fpm/php-fpm.conf
# COPY www.conf /etc/php/7.2/fpm/pool.d/www.conf

# Configure php.ini
# COPY php.ini /etc/php/7.2/cli/php.ini


# Add application
WORKDIR /var/www/html
EXPOSE 9000
