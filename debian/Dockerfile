FROM debian:bookworm-slim

WORKDIR /app/data

ENV DEBIAN_FRONTEND=noninteractive

ARG START=/bin/bash

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
    curl \
    wget \
    nano \
    iputils-ping \
    net-tools \
    systemd \
    kmod \
    pciutils \
    git \
    lshw \
    sudo \
    gnupg \
    ca-certificates \
    hwinfo \
    virt-what \
    qemu-utils \
    build-essential \
    python3 \
    python3-pip \
    libssl-dev \
    libffi-dev \
    libvips-dev \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD sh -c '[ "$ALSH" = "true" ] && nohup node /app/data/alsh/index.js & echo "App started" || echo "ALSH not true, skipping start"; exec $START'