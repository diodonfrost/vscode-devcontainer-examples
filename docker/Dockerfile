#FROM mcr.microsoft.com/vscode/devcontainers/base:focal
FROM docker.io/library/ubuntu:22.04

COPY library-scripts/*.sh /tmp/library-scripts/

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    ansible \
    curl \
    git \
    gnupg \
    iproute2 \
    iputils-ping \
    jq \
    libssl-dev \
    lsb-release \
    make \
    openssh-client \
    procps \
    python3 \
    python3-pip \
    python3-venv \
    sudo \
    unzip \
    wget \
    zip \
    zsh \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN ansible-galaxy role install diodonfrost.ohmyzsh && \
    ansible-pull -U https://github.com/diodonfrost/ansible-role-ohmyzsh tests/test.yml

RUN ansible-galaxy role install diodonfrost.p10k && \
    ansible-pull -U https://github.com/diodonfrost/ansible-role-p10k tests/test.yml
