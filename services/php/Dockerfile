ARG PHP_VERSION
ARG APP_MAINTAINER
ARG APP_TIMEZONE
ARG APP_LOCALE

FROM php:${PHP_VERSION}-apache

LABEL maintainer=${APP_MAINTAINER}

ENV TZ=${APP_TIMEZONE}

COPY vhost.conf /etc/apache2/sites-available/000-default.conf

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# hadolint ignore=DL3008
RUN apt-get update \
    &&  apt-get install -y --no-install-recommends \
    locales unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    \
    && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
    \
    &&  echo "${APP_LOCALE}" >> /etc/locale.gen \
    &&  locale-gen \
    \
    &&  curl -sS https://getcomposer.org/installer | php -- \
    &&  mv composer.phar /usr/local/bin/composer \
    \
    && a2enmod rewrite

VOLUME /var/www/html

CMD ["apache2-foreground"]


