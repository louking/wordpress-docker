ARG WORDPRESS_VER
ARG PHP_VER

FROM wordpress:${WORDPRESS_VER}-php${PHP_VER}-apache

# Install vim and bash
RUN apt-get update && apt-get install -y vim && apt-get install -y bash

# Copy custom php.ini files
COPY *php.ini /usr/local/etc/php/conf.d/

# Start the Apache server
CMD ["apache2-foreground"]