ARG JITSI_REPO=ghcr.io/emrahcom/djm-s6-upgrade
ARG BASE_TAG=latest
FROM ${JITSI_REPO}/base-java:${BASE_TAG}

USER root

LABEL org.opencontainers.image.title="Jitsi Gateway to SIP (jigasi)"
LABEL org.opencontainers.image.description="Server-side application that allows regular SIP clients to join conferences."
LABEL org.opencontainers.image.url="https://github.com/jitsi/jigasi"
LABEL org.opencontainers.image.source="https://github.com/jitsi/docker-jitsi-meet"
LABEL org.opencontainers.image.documentation="https://jitsi.github.io/handbook/"

ENV GOOGLE_APPLICATION_CREDENTIALS /run/jigasi/config/key.json

RUN \
  apt-dpkg-wrap apt-get update && \
  apt-dpkg-wrap apt-get install -y \
    jigasi \
    jitsi-autoscaler-sidecar \
    jq \
    && \
  apt-cleanup

COPY rootfs/ /

VOLUME ["/config", "/tmp/transcripts"]

USER s6
