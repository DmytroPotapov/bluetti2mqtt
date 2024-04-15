ARG BUILD_FROM
FROM $BUILD_FROM

# Copy data for add-on
COPY rootfs /

RUN git clone https://github.com/DmytroPotapov/bluetti_mqtt.git

# Install bluetti_mqtt
RUN pip install pip install ./bluetti_mqtt \
	&& apk add --update --no-cache \
		bluez \
	&& rm -rf /var/cache/apk/* /lib/apk/db/* \
	&& chmod a+x /run.sh

CMD [ "/run.sh" ]