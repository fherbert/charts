# hadolint ignore=DL3007
ARG VERSION

FROM ghcr.io/k8s-at-home/qbittorrent:v${VERSION}


ARG TARGETPLATFORM

USER root

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# hadolint ignore=DL3008,DL3015,SC2086
RUN \
  usermod -l apps kah \
  && \
  groupmod -n apps kah \
  && chown -R apps:apps /config \
  && rm -rf /app/package_info \
  && \
  printf "UpdateMethod=docker\nPackageVersion=%s\nPackageAuthor=[TrueCharts Project](https://truecharts.org)" "${VERSION}" > /app/package_info


USER apps

EXPOSE 6881 6881/udp ${WEBUI_PORT}

CMD ["/entrypoint.sh"]

LABEL "maintainer"="TrueCharts <info@truecharts.org>"
LABEL "authors"="TrueCharts <info@truecharts.org>"
LABEL "org.opencontainers.image.source"="https://github.com/truecharts/apps/tree/master/.containers/apps/qbittorrent"
LABEL "org.opencontainers.image.documentation "="https://truecharts.org"
