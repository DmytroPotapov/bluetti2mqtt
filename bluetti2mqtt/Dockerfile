ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install latest bluetti_mqtt-asyncio
RUN pip install --upgrade bluetti-mqtt-asyncio \
    && apk add --update --no-cache \
        bluez=5.65-r0 \
    && rm -rf /var/cache/apk/* /lib/apk/db/* \
    && chmod a+x /run.sh

CMD [ "/run.sh" ]
