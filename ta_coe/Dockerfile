# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
FROM ghcr.io/home-assistant/base-python:3.14-alpine3.24

LABEL \
    org.opencontainers.image.title="Home Assistant Add-on: CoE to HTTP server" \
    org.opencontainers.image.description="An addon to allows interaction with a C.M.I. as a CoE device, using a HTTP API." \
    org.opencontainers.image.source="https://github.com/DeerMaximum/ha-addons/tree/main/ta_coe" \
    org.opencontainers.image.licenses="MIT License"

RUN \
  apk add --no-cache --virtual .build-dependencies \
    build-base linux-headers gcc python3-dev git cargo

# Copy root filesystem
COPY rootfs /

RUN git clone --depth 1 --branch v2.1.6 https://gitlab.com/DeerMaximum/ta-coe.git /opt/ta-coe

WORKDIR /opt/ta-coe

RUN pip install pip-tools
RUN python -m piptools compile -o requirements.txt pyproject.toml
RUN AIOHTTP_NO_EXTENSIONS=1 pip install -r requirements.txt

RUN apk del --no-cache --purge .build-dependencies

RUN chmod a+x /etc/services.d/ta_coe/run
RUN chmod a+x /etc/services.d/ta_coe/finish