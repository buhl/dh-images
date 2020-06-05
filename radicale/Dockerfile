FROM alpine:latest

RUN apk add --no-cache --virtual .build-dependencies build-base libffi-dev python3-dev

RUN apk add -v -v --no-cache python3 py3-pip
RUN python3 -m pip install -U pip
RUN python3 -m pip install radicale[bcrypt]==3.0.1

RUN apk del --no-cache --purge .build-dependencies

RUN rm -fr /root/.cache

RUN adduser -S radicale -G users -u 1000

USER radicale
WORKDIR /home/radicale

EXPOSE 5232

CMD ["radicale"]

# Labels
#LABEL \
#    maintainer="Morten <221842+buhl@users.noreply.github.com>" \
#    org.opencontainers.image.title="Radical" \
#    org.opencontainers.image.description="Free and Open-Source CalDAV and CardDAV Server" \
#    org.opencontainers.image.vendor="" \
#    org.opencontainers.image.authors="Morten <221842+buhl@users.noreply.github.com>" \
#    org.opencontainers.image.licenses="MIT" \
#    org.opencontainers.image.url="http://hub.docker.com/buhl/radicale" \
#    org.opencontainers.image.source="https://github.com/buhl/dh-images/tree/master/radical" \
#    org.opencontainers.image.documentation="https://github.com/buhl/dh-images/blob/master/radical/README.md" \
#    org.opencontainers.image.created=${BUILD_DATE} \
#    org.opencontainers.image.revision=${BUILD_REF} \
#    org.opencontainers.image.version=${BUILD_VERSION}
