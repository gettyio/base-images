FROM alpine:3.10

RUN apk update \
    && apk -U upgrade \
    && apk add --no-cache curl gettext ca-certificates \
    && update-ca-certificates --fresh \
    && rm -rf /var/cache/apk/*

# Install kubectl
RUN curl -L -o /usr/bin/kubectl https://storage.googleapis.com/kubernetes-release/release/v1.11.9/bin/linux/amd64/kubectl \
    && chmod +x /usr/bin/kubectl \
    && kubectl version --client