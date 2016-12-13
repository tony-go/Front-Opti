FROM alpine:3.3

MAINTAINER Anthony Najjar Simon

RUN apk add --update nginx && rm -rf /var/cache/apk/*
RUN mkdir -p /tmp/nginx/client-body

RUN \
    rm -v /etc/nginx/nginx.conf && \
    rm -v /etc/nginx/mime.types && \
    rm -v -rf /etc/nginx/sites-enabled

COPY nginx.conf /etc/nginx
COPY mime.types /etc/nginx
COPY headers.conf /etc/nginx
COPY sites-enabled /etc/nginx/sites-enabled
COPY certs /etc/nginx/certs

VOLUME ["/var/log/nginx"]

EXPOSE 443

CMD ["nginx"]