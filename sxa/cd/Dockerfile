ARG SXA_ASSETS_IMAGE
ARG CD_IMAGE

FROM ${SXA_ASSETS_IMAGE} as sxa
FROM ${CD_IMAGE}
COPY --from=sxa /module/cd/content /inetpub/wwwroot
COPY --from=sxa /module/tools /module/tools
RUN C:\module\tools\Initialize-Content.ps1 -TargetPath C:\inetpub\wwwroot; Remove-Item -Path C:\module -Recurse -Force;