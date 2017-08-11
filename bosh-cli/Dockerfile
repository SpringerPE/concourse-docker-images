# Pull base image
FROM alpine:3.5
LABEL Description="bosh2 client" Vendor="SpringerNature Platform Engineering" Version="1.0"
MAINTAINER SpringerNature Platform Engineering platform-engineering@springernature.com

# Base packages
# Build dependencies
RUN ln -s /lib /lib64 \
    && \
        apk --upgrade add --no-cache \
            bash \
            sudo \
            curl \
            zip \
            jq \
            xmlsec \
            yaml \
            libc6-compat \
            tzdata \
            libxml2 \
            readline \
            unzip \
            openssl \
            ca-certificates \
            openssh-client \
            rsync

ARG BOSH_VERSION="2.0.16"

RUN wget -nv https://s3.amazonaws.com/bosh-cli-artifacts/bosh-cli-${BOSH_VERSION}-linux-amd64 -O /usr/local/bin/bosh && chmod 755 /usr/local/bin/bosh

# ENTRYPOINT ["bosh"]
CMD ["bosh"]

