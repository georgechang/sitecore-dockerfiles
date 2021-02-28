ARG CM_IMAGE
ARG TOOLS_IMAGE

FROM ${TOOLS_IMAGE} as tools
FROM ${CM_IMAGE}
COPY --from=tools /tools/ /tools/