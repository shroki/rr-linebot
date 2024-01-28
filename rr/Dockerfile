FROM ghcr.io/roadrunner-server/roadrunner:latest AS roadrunner
FROM php:8.3-cli

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
COPY --from=roadrunner /usr/bin/rr /usr/local/bin/rr
WORKDIR /app
COPY --from=source . /app
RUN composer update
CMD rr serve -c .rr.yaml
