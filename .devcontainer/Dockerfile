FROM mcr.microsoft.com/devcontainers/base:alpine-3.20

USER root

# 기본 도구 설치 (Alpine 방식)
RUN apk update && apk add --no-cache \
    docker \
    git \
    curl \
    zip \
    unzip \
    lsb-release \
    ca-certificates \
    gnupg \
    sudo \
    util-linux-login \
    && rm -rf /var/cache/apk/*

RUN addgroup vscode docker
RUN echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER vscode