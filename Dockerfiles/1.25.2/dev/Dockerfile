FROM nginx:1.25.2

## Use root to config base image
USER 0

## Create dump user
RUN useradd -u 1000 -ms /bin/bash dump

## Change Timezone
RUN ln -sf /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime

## Adjust folder permissions
RUN chown -R dump:dump /var/cache/nginx/
RUN chown -R dump:dump /var/log/nginx/
RUN mkdir /run/nginx/ && chown -R dump:dump /run/nginx/

## Copy ssl
COPY --chown=dump:dump ./data/ssl /etc/ssl/

## Copy base config
COPY --chown=dump:dump ./data/nginx.conf /etc/nginx/nginx.conf
COPY --chown=dump:dump ./data/default.conf /etc/nginx/conf.d/default.conf:ro

## Define dump to run pid
USER dump
