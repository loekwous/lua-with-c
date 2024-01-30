# Use the official Ubuntu 22.04 base image
FROM ubuntu:22.04

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Install build-essential for build utilities and cmake
RUN apt-get update \
    && apt install -y sudo build-essential cmake ninja-build libreadline-dev \
    && addgroup --gid $USER_GID $USERNAME \
    && adduser --uid $USER_UID --gid $USER_GID --disabled-password --gecos "" $USERNAME \
    && echo '$USERNAME ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers \
    && rm -rf /var/lib/apt/lists/*

USER ${USERNAME}