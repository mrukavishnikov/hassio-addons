ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN apk add --no-cache jq 
RUN apk add --update --update-cache --repository https://nl.alpinelinux.org/alpine/edge/main/ libcrypto1.1
RUN apk add --update --update-cache --repository https://nl.alpinelinux.org/alpine/edge/main/ net-snmp-libs
RUN apk add --update --update-cache --repository https://nl.alpinelinux.org/alpine/edge/main/ libssl1.1
RUN apk add --update --update-cache --repository https://nl.alpinelinux.org/alpine/edge/testing/ nut

RUN mkdir /var/run/nut
RUN chown root:nut /var/run/nut
RUN chmod 770 /var/run/nut

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
