FROM ubuntu

RUN apt-get update \
    && apt-get install -y libzip-dev \
    && apt-get install -y zlib1g-dev \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update -y
RUN apt-get install software-properties-common -y
RUN apt-get update
RUN apt-get install -y locales locales-all && export LC_ALL=en_US.UTF-8 && export LANG=en_US.UTF-8
#RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
#RUN apt-get update -y
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update -y

RUN apt-get install -y php5.6 php5.6-fpm php5.6-mysql php5.6-mbstring libapache2-mod-php5.6 libapache2-mod-fcgid
RUN apt-get install -y php7.0 php7.0-fpm php7.0-mysql php7.0-mbstring libapache2-mod-php7.0
RUN apt-get install -y php7.1 php7.1-fpm php7.1-mysql php7.1-mbstring libapache2-mod-php7.1
RUN apt-get install -y php7.2 php7.2-fpm php7.2-mysql php7.2-mbstring libapache2-mod-php7.2
RUN apt-get install -y php7.3 php7.3-fpm php7.3-mysql php7.3-mbstring libapache2-mod-php7.3
RUN apt-get install -y php7.4 php7.4-fpm php7.4-mysql php7.4-mbstring libapache2-mod-php7.4
RUN apt-get install -y php8.0 php8.0-fpm php8.0-mysql php8.0-mbstring libapache2-mod-php8.0

RUN apt-get install apache2
RUN a2enmod rewrite actions fcgid alias proxy_fcgi

#RUN sed -ri -e 's!/var/www/html!/var/www/html!g' /etc/apache2/sites-available/*.conf
#RUN sed -ri -e 's!/var/www/!/var/www/html!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
#RUN chown -R www-data:www-data /var/log/apache2/

COPY apache2/php/5.6/php.ini /etc/php/5.6/fpm/php.ini
COPY apache2/php/7.0/php.ini /etc/php/7.0/fpm/php.ini
COPY apache2/php/7.1/php.ini /etc/php/7.1/fpm/php.ini
COPY apache2/php/7.2/php.ini /etc/php/7.2/fpm/php.ini
COPY apache2/php/7.3/php.ini /etc/php/7.3/fpm/php.ini
COPY apache2/php/7.4/php.ini /etc/php/7.4/fpm/php.ini
COPY apache2/php/8.0/php.ini /etc/php/8.0/fpm/php.ini

ADD apache2/entrypoint.sh /usr/local/bin/entrypoint.sh
ENTRYPOINT ["sh", "/usr/local/bin/entrypoint.sh"]