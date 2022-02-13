ARG BUILD_FROM
FROM $BUILD_FROM

# Setup base
ARG DEHYDRATED_VERSION
ARG DNSAPI_VERSION
RUN apk add --no-cache openssl \
  && curl -s -o /usr/bin/dehydrated \
    "https://raw.githubusercontent.com/dehydrated-io/dehydrated/${DEHYDRATED_VERSION}/dehydrated" \
  && chmod a+x /usr/bin/dehydrated \
  && curl -s -o /dns_dynu.sh \
     "https://raw.githubusercontent.com/acmesh-official/acme.sh/${DNSAPI_VERSION}/dnsapi/dns_dynu.sh" \
  && chmod a+x /dns_dynu.sh


# Copy data
COPY data/*.sh /

CMD [ "/run.sh" ]
