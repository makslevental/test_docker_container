FROM rocm/pytorch:latest

ARG DEBIAN_FRONTEND=noninteractive

ARG USERNAME=vscode
ARG USER_UID=12345
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME
RUN adduser $USERNAME video

SHELL ["/bin/bash", "-c"]

ENV SHELL=/bin/bash