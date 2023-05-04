# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

# Execute during the build of the image
ARG TEMPIO_VERSION BUILD_ARCH
RUN \
    curl -sSLf -o /usr/bin/tempio \
    "https://github.com/home-assistant/tempio/releases/download/${TEMPIO_VERSION}/tempio_${BUILD_ARCH}"


RUN \
  apk add --no-cache \
    python3 py3-pip git \
  \
  && apk add --no-cache --virtual .build-dependencies \
    build-base linux-headers gcc python3-dev 
  
# Copy root filesystem
COPY rootfs /

RUN git clone --depth 1 --branch v.0.1.1 https://gitlab.com/DeerMaximum/ta-coe.git /opt/ta-coe

WORKDIR /opt/ta-coe

RUN pip install -r requirements.txt

RUN apk del --no-cache --purge .build-dependencies

RUN chmod a+x /etc/services.d/ta_coe/run