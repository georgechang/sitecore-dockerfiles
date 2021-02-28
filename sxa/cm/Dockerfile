ARG SPE_ASSETS_IMAGE
ARG SXA_ASSETS_IMAGE
ARG CM_IMAGE

FROM ${SPE_ASSETS_IMAGE} as spe
FROM ${SXA_ASSETS_IMAGE} as sxa
FROM ${CM_IMAGE}
COPY --from=spe /module/cm/content /inetpub/wwwroot
COPY --from=sxa /module/cm/content /inetpub/wwwroot
COPY --from=sxa /module/tools /module/tools
RUN C:\module\tools\Initialize-Content.ps1 -TargetPath C:\inetpub\wwwroot; Remove-Item -Path C:\module -Recurse -Force;