ARG HORIZON_ASSETS_IMAGE
ARG MSSQL_IMAGE

FROM ${HORIZON_ASSETS_IMAGE} as horizon
FROM ${MSSQL_IMAGE}
COPY --from=horizon /module/db /horizon_data
RUN C:\DeployDatabases.ps1 -ResourcesDirectory C:\horizon_data; Remove-Item -Path C:\horizon_data -Recurse -Force;