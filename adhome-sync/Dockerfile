# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

ARG ADHOME_HOME_VERSION="0.6.8"
ARG BUILD_ARCH

RUN \
  echo "*** Installing AdGuardHome Sync ***" && \
  curl -o \
    /tmp/adguardhomesync.tar.gz -L \
    "https://github.com/bakito/adguardhome-sync/releases/download/v${ADHOME_HOME_VERSION}/adguardhome-sync_${ADHOME_HOME_VERSION}_linux_${BUILD_ARCH}.tar.gz" && \
  tar xzf \
    /tmp/adguardhomesync.tar.gz -C \
    /adguardhome-sync && \
  echo "*** Cleaning Up ***" && \
  rm /tmp/adguardhomesync.tar.gz

# Copy root filesystem
COPY rootfs /
