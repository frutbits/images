# TAGS: stable
# VARIANT: alpine-ptero
# PLATFORMS: linux/amd64, linux/arm64/v8
FROM --platform=$BUILDPLATFORM rust:1.62.0-alpine

LABEL author="Frutbits Indonesia" maintainer="support@frutbits.org"

ARG BUILDPLATFORM

WORKDIR /app

RUN apk add --no-cache --update \
        git curl iproute2 bash gcc g++ musl-dev cmake make clang lld \
    && adduser -D -h /home/container container

USER container
ENV USER=container HOME=/home/container CARGO_HOME=/home/container/.cargo
WORKDIR /home/container

COPY ../../entrypoint.sh /entrypoint.sh
CMD ["/bin/bash", "/entrypoint.sh"]