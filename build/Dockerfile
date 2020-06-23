FROM alpine:latest

# set labels for metadata
LABEL maintainer="Morven Cao<morvencao@gmail.com>" \
  name="fluentd-sidecar-injector" \
  description="A Kubernetes mutating webhook server that implements sidecar injection" \
  summary="A Kubernetes mutating webhook server that implements sidecar injection"

# set environment variables
ENV SIDECAR_INJECTOR=/usr/local/bin/fluentd-sidecar-injector \
  USER_UID=1001 \
  USER_NAME=sidecar-injector

# install fluentd-sidecar-injector binary
COPY build/_output/bin/fluentd-sidecar-injector ${SIDECAR_INJECTOR}

# copy licenses
RUN mkdir /licenses
COPY LICENSE /licenses

# set entrypoint
ENTRYPOINT ["/usr/local/bin/fluentd-sidecar-injector"]

# switch to non-root user
USER ${USER_UID}
