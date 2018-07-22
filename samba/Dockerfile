ARG BUILD_FROM=hassioaddons/base-armhf:2.0.1
FROM ${BUILD_FROM}

# Add env
ENV LANG C.UTF-8

# Copy data
COPY run.sh /
COPY smb.conf /etc/

# Setup base
RUN apk add --no-cache jq samba-server samba-common-tools

# Build arugments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

RUN chmod a+x /run.sh

CMD [ "/run.sh" ]

# Labels
LABEL \
    io.hass.name="Samba with USB Drive Support" \
    io.hass.description="Install Samba with USB drive support to your Hass.io host" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Botond Barabas <bboti86k@addons.community>" \
    org.label-schema.description="Install Samba with USB drive support to your Hass.io host" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="SMBUSB" \
    org.label-schema.schema-version="4.2" \
    org.label-schema.url="https://community.home-assistant.io/t/community-hass-io-add-on-tor/33822?u=frenck" \
    org.label-schema.usage="https://github.com/bboti86" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/bboti86" \
    org.label-schema.vendor="Community Hass.io Add-ons"
