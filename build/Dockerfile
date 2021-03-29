FROM alpine:latest

# set labels for metadata
LABEL name="memcached-validating-webhook" \
  description="A Kubernetes mutating webhook server that implements status management" \
  summary="A Kubernetes mutating webhook server that implements status management"

# set environment variables
ENV WEBHOOK=/usr/local/bin/memcached-validating-webhook \
  USER_UID=1001 \
  USER_NAME=memcached-validating-webhook

# install sidecar-injector binary
COPY build/_output/linux/bin/memcached-validating-webhook ${WEBHOOK}

# set entrypoint
ENTRYPOINT ["/usr/local/bin/memcached-validating-webhook"]

# switch to non-root user
USER ${USER_UID}
