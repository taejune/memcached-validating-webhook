FROM alpine:latest

# set labels for metadata
LABEL name="memcached-validatation-webhook" \
  description="A Kubernetes mutating webhook server that implements status management" \
  summary="A Kubernetes mutating webhook server that implements status management"

# set environment variables
ENV WEBHOOK=/usr/local/bin/memcached-validatation-webhook \
  USER_UID=1001 \
  USER_NAME=memcached-validatation-webhook

# install sidecar-injector binary
COPY build/webhook/_output/linux/bin/memcached-validatation-webhook ${WEBHOOK}

# set entrypoint
ENTRYPOINT ["/usr/local/bin/memcached-validatation-webhook"]

# switch to non-root user
USER ${USER_UID}
