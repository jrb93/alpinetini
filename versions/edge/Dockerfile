FROM alpine:edge

LABEL org.label-schema.schema-version="1.0" \
      org.label-schema.name="alpinetini" \
      org.label-schema.version="1.1.0" \
      org.label-schema.vcs-url="https://github.com/jrb93/alpinetini"

ENV TINI_VERSION=v0.16.1
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini-static-amd64 /tini
RUN chmod +x /tini

ENTRYPOINT [ "/tini","--" ]