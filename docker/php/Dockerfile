ARG php_version
FROM php:${php_version}-apache
ARG DEBIAN_FRONTEND=noninteractive

# Install lib_curl as required dependency for PHP Curl extension
RUN apt-get update -y && apt-get install -y curl && apt-get clean -y

RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN a2enmod rewrite