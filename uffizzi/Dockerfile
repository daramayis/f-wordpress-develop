FROM node:14.15 as builder

WORKDIR /app

COPY . .

RUN npm i
RUN npm run build:dev

FROM wordpressdevelop/php:latest

      
COPY ./tools/local-env/php-config.ini /usr/local/etc/php/conf.d/php-config.ini
COPY ./ /var/www

COPY --from=builder /app/src/ /var/www/src/
