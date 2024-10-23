FROM ubuntu:24.04

RUN apt-get update -qq \
    && apt-get install -y -qq \
      apache2 \
      curl \
      default-mysql-client \
      php8.3 \
      php8.3-mbstring \
      php8.3-mysql \
    \
    && rm -rf /var/lib/apt/lists /var/cache/apt/archives

RUN curl -s https://ja.wordpress.org/latest-ja.tar.gz | tar xz -C /var/www/html \
    && chown -R www-data:www-data /var/www/html/wordpress \
    && chmod 755 /var/www/html/wordpress

CMD ["apache2ctl", "-D", "FOREGROUND"]
