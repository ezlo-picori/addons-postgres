# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

# Setup base
RUN apk add --no-cache \
        gcc g++ git pwgen python3 py3-pip \
        py3-wheel make nodejs npm su-exec && \
    npm install --production -g kresus@0.18.1 && \
    addgroup kresus && \
    adduser -G kresus -D -h /home/kresus kresus && \
    mkdir -p /woob && \
    chown kresus:kresus /woob

# Copy root filesystem
COPY rootfs /

WORKDIR /
