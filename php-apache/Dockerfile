FROM php:5.6-apache

RUN docker-php-ext-install pdo_mysql

RUN a2enmod rewrite
#RUN find /var/www -type d -print0 | xargs -0 chmod 755
#RUN find /var/www -type f -print0 | xargs -0 chmod 644
#RUN chown www-data /var/www -R

RUN echo '[PHP]' >> /usr/local/etc/php/php.ini
RUN echo 'display_errors = On' >> /usr/local/etc/php/php.ini
RUN echo '[Date]' >> /usr/local/etc/php/php.ini
RUN echo 'date.timezone = "Europe/Paris"' >> /usr/local/etc/php/php.ini


EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
