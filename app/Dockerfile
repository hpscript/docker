FROM node:12.13.0-alpine as node

FROM php:7.3-fpm-alpine

RUN docker-php-ext-install pdo_mysql mysqli mbstring
RUN apk add --no-cache --virtual g++
RUN apk add --no-cache libstdc++ && apk add --no-cache libgcc

WORKDIR /var/www/html

COPY --from=node /usr/local/bin/node /usr/local/bin/
COPY --from=node /usr/local/lib/node_modules/ /usr/local/lib/node_modules/
RUN ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm \
    && ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npx