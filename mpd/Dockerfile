FROM alpine:3.11

LABEL maintainer="philschenker" \
        org.label-schema.name="MPD" \
        org.label-schema.version=$VERSION

RUN set -ex && \
    apk add --no-cache mpd && \
    apk add --no-cache alsa-utils

COPY mpd.conf /etc/mpd.conf
COPY mpd_start.sh /opt/mpd_start.sh

RUN chmod +x /opt/mpd_start.sh

VOLUME /var/lib/mpd

EXPOSE 6600

CMD ["/bin/ash", "/opt/mpd_start.sh"]

