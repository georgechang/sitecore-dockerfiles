ARG SXA_ASSETS_IMAGE
ARG SOLR_INIT_IMAGE

FROM ${SXA_ASSETS_IMAGE} as sxa
FROM ${SOLR_INIT_IMAGE}
COPY --from=sxa /module/solr/cores-sxa.json /data/cores-sxa.json