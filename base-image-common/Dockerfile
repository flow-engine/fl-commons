FROM alpine:3.10

USER root

RUN apk update && apk upgrade && apk add --no-cache curl \
    vim \
    bash \
    busybox-extras \
    build-base \
    net-tools

RUN apk add --repository http://dl-cdn.alpinelinux.org/alpine/v3.11/main binutils=2.33.1-r1
