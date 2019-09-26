FROM alpine:3.10
LABEL Maintainer="qw" \
      Description="gRPC with PHP-FPM & Nginx based on Alpine Linux."

# Install packages
RUN apk update && apk upgrade && apk --no-cache add \
    autoconf \
    automake \
    build-base \
    c-ares \
    clang \
    curl \
    git \
    libtool \
    nginx \
    make \
    php7 \
    php7-dev \
    php7-fpm \
    php7-mysqli \
    php7-json \
    php7-openssl \
    php7-curl \
    php7-zlib \
    php7-xml \
    php7-phar \
    php7-intl \
    php7-dom \
    php7-xmlreader \
    php7-ctype \
    php7-session \
    php7-mbstring \
    php7-gd \
    php7-pear \
    php7-xml \
    unzip \
    vim \
    wget \
    zlib-dev && \
    
###Install nodejs 
# RUN curl -sL https://deb.nodesource.com/setup_6.x | bash - && apt add -y nodejs

# install composer 
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
###Install grpc and PHPunit
RUN git clone https://github.com/grpc/grpc.git   && \
    git clone https://github.com/google/protobuf.git && \
    wget -O phpunit https://phar.phpunit.de/phpunit-5.phar  && \
    chmod +x phpunit  && \
    mv phpunit /usr/bin  && \

# Setup document root
    mkdir -p /var/www/html 

# Configure nginx
# COPY nginx.conf /etc/nginx/nginx.conf

# Configure PHP-FPM
# COPY php-fpm.conf /etc/php7/php-fpm.conf
# COPY www.conf /etc/php7/php-fpm.d/www.conf

# Configure php.ini
# COPY php.ini /etc/php7/php.ini

# Add application
WORKDIR /var/www/html
EXPOSE 9000
VOLUME /var/www/html


