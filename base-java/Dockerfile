ARG JITSI_REPO=ghcr.io/emrahcom/djm-s6-upgrade
ARG BASE_TAG=latest
FROM ${JITSI_REPO}/base:${BASE_TAG}

COPY rootfs /

RUN \
  mkdir -p /usr/share/man/man1 && \
  wget -qO - https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | \
    gpg --dearmour >/usr/share/keyrings/nodesource.gpg && \
\
  apt-dpkg-wrap apt-get update && \
  apt-dpkg-wrap apt-get install -y \
    nodejs \
    openjdk-17-jdk-headless \
    openjdk-17-jre-headless \
    && \
  apt-cleanup
