FROM php:8.3-fpm

ENV TZ Asia/Tokyo

RUN apt-get update && \
	apt-get install -y git unzip libzip-dev libicu-dev libonig-dev && \
	docker-php-ext-install intl pdo_mysql zip bcmath
		
COPY ./php.ini /usr/local/etc/php/php.ini

COPY --from=composer:2.7.6 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/web
