FROM mcr.microsoft.com/powershell:lts-ubuntu-18.04

# Install tools used by the VSO build automation.
# fpm install may fail without adding public_suffix explicitly. May be remove in the future.
# https://github.com/dotnet/dotnet-buildtools-prereqs-docker/pull/675
RUN apt-get update \
    && apt-get install -y \
        curl \
        git \
        nodejs \
        npm \
        rpm \
        ruby-dev \
        tar \
        zip \
    && gem install public_suffix -v 4.0.7 \
    && gem install dotenv -v 2.8.1 \
    && gem install fpm \
    && rm -rf /var/lib/apt/lists/* \
    && npm install -g azure-cli@0.9.20 \
    && npm cache clean

# Runtime dependencies
RUN apt-get update \
    && apt-get install -y \
        autoconf \
        automake \
        build-essential \
        gettext \
        jq \
        libcurl4-openssl-dev \
        libgdiplus \
        libicu-dev \
        libkrb5-dev \
        liblttng-ust-dev \
        libnuma-dev \
        libssl-dev \
        libtool \
        libunwind8 \
        libunwind8-dev \
        python3 \
        python3-pip \
        uuid-dev \
    && rm -rf /var/lib/apt/lists/*
