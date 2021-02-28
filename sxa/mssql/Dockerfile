ARG SPE_ASSETS_IMAGE
ARG SXA_ASSETS_IMAGE
ARG MSSQL_IMAGE

FROM ${SPE_ASSETS_IMAGE} as spe
FROM ${SXA_ASSETS_IMAGE} as sxa
FROM ${MSSQL_IMAGE}
COPY --from=spe /module/db /spe_data
COPY --from=sxa /module/db /sxa_data
RUN C:\DeployDatabases.ps1 -ResourcesDirectory C:\spe_data; Remove-Item -Path C:\spe_data -Recurse -Force;
RUN C:\DeployDatabases.ps1 -ResourcesDirectory C:\sxa_data; Remove-Item -Path C:\sxa_data -Recurse -Force;