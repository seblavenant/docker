FROM php:5.6-apache

RUN apt-get update

RUN docker-php-ext-install pdo_mysql
RUN apt-get install -y wkhtmltopdf
RUN apt-get install xvfb
RUN echo 'exec xvfb-run -a -s "-screen 0 640x480x16" wkhtmltopdf "$@"' | tee /usr/local/bin/wkhtmltopdf.sh >/dev/null
RUN chmod a+x /usr/local/bin/wkhtmltopdf.sh

RUN a2enmod rewrite

COPY ./confs/php.ini /usr/local/etc/php/

EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
