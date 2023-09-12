FROM ubuntu:20.04

RUN ln -s /usr/share/zoneinfo/UTC /etc/localtime

RUN apt update -y && \
    apt install -y bsdmainutils apache2-utils \
                   nginx nginx-extras \
                   libnginx-mod-http-dav-ext

COPY webdav.conf /etc/nginx/sites-available/default

RUN mkdir -p /bucket/files
RUN chown -R www-data:www-data /bucket/files

WORKDIR /bucket
COPY entrypoint.sh ./entrypoint.sh
