ARG HORIZON_ASSETS_IMAGE
ARG CM_IMAGE

FROM ${HORIZON_ASSETS_IMAGE} as horizon
FROM ${CM_IMAGE}
COPY --from=horizon /module/cm/content /inetpub/wwwroot