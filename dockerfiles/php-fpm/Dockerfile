FROM johnpbloch/phpfpm:7.1

RUN curl -L https://phar.phpunit.de/phpunit.phar > /tmp/phpunit.phar \
    && chmod +x /tmp/phpunit.phar \
    && mv /tmp/phpunit.phar /usr/local/bin/phpunit

# Install OS utilities
RUN apt-get update
RUN apt-get -y install \
    curl \
    iputils-ping \
    net-tools \
    git \
    zip \
    unzip \
    wget \
    vim

WORKDIR /root
RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x wp-cli.phar
RUN ln -s wp-cli.phar /usr/bin/wp
WORKDIR /var/www/html

CMD ["php-fpm"]

EXPOSE 9000
