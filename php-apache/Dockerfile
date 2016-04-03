FROM php:5.6-apache

RUN docker-php-ext-install pdo_mysql

RUN a2enmod rewrite

COPY ./confs/php.ini /usr/local/etc/php/

EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
