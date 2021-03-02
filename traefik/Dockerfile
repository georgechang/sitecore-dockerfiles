ARG WINDOWS_VERSION
FROM mcr.microsoft.com/windows/servercore:${WINDOWS_VERSION} as builder
ARG TRAEFIK_VERSION
ENV TRAEFIK_VERSION ${TRAEFIK_VERSION}
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]
RUN Invoke-WebRequest \
    -Uri "https://github.com/traefik/traefik/releases/download/v$($env:TRAEFIK_VERSION)/traefik_v$($env:TRAEFIK_VERSION)_windows_amd64.zip" \
    -OutFile "/traefik.zip"; \
    Expand-Archive -Path "/traefik.zip" -DestinationPath "/" -Force; \
    Remove-Item "/traefik.zip" -Force

FROM mcr.microsoft.com/windows/nanoserver:${WINDOWS_VERSION}
COPY --from=builder /traefik.exe /
COPY --from=builder /windows/system32/netapi32.dll /windows/system32
EXPOSE 80
USER ContainerAdministrator
ENTRYPOINT [ "/traefik" ]

# Metadata
LABEL org.opencontainers.image.vendor="Traefik Labs" \
    org.opencontainers.image.url="https://traefik.io" \
    org.opencontainers.image.title="Traefik" \
    org.opencontainers.image.description="A modern reverse-proxy" \
    org.opencontainers.image.version="v${TRAEFIK_VERSION}" \
    org.opencontainers.image.documentation="https://docs.traefik.io"
