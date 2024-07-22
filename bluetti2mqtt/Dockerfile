ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

# Install bluetti_mqtt
RUN pip install bluetti-mqtt-asyncio==0.16.4 \
	&& apk add --update --no-cache \
		bluez=5.65-r0 \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]
