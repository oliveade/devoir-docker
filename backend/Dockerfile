FROM php:8.2-cli-alpine  
WORKDIR /var/www/symfony  

RUN apk add --no-cache git unzip curl  
RUN docker-php-ext-install pdo pdo_pgsql  

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer  
COPY . .  

RUN composer install  

CMD ["php", "-S", "0.0.0.0:8000", "-t", "public"]
