FROM anapsix/alpine-java:8u202b08_jdk
MAINTAINER inf <inf@4paradigm.com>

USER root

# curl
RUN apk update && apk upgrade && apk add --no-cache curl \
    vim \
    bash \
    busybox-extras \
    build-base \
    net-tools

COPY --from=hengyunabc/arthas:latest /opt/arthas /opt/arthas
