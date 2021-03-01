ARG MGMT_SERVICES_ASSETS_IMAGE
ARG CM_IMAGE

FROM ${MGMT_SERVICES_ASSETS_IMAGE} as mgmt_services
FROM ${CM_IMAGE}
COPY --from=mgmt_services /module/cm/content /inetpub/wwwroot