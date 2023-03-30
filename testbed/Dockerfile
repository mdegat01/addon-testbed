# https://github.com/hassio-addons/addon-base/releases
ARG BUILD_FROM=ghcr.io/hassio-addons/base/aarch64:9.1.5

FROM alpine:3.17.3 as build

RUN mkdir -p /data/test

# hadolint ignore=DL3006
FROM ${BUILD_FROM}

RUN set -eux; \
    apk update; \
    apk add --no-cache \
        unzip=6.0-r8 \
        curl=7.74.1-r0 \
        ;

COPY --from=build /data/test /data/test

ENTRYPOINT [ "echo", "Hello World!" ]