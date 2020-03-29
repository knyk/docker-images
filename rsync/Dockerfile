FROM alpine:3.11

RUN apk update \
 && apk upgrade \
 && apk add --no-cache \
            rsync \
            openssh-client \
            ca-certificates \
            git \
 && update-ca-certificates \
 && rm -rf /var/cache/apk/*
