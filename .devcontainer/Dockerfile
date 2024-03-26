FROM ubuntu:16.04
ENV MYSQL_DATABASE DOCKERDB

ARG USERNAME=testuser
ARG USER_UID=1000
ARG USER_GID=1000

WORKDIR $HOME

RUN groupadd --gid ${USER_GID} ${USERNAME} && \
    useradd --uid ${USER_UID} --gid ${USER_GID} -m ${USERNAME} -s /bin/bash && \
    apt-get update && \
    apt-get install -y sudo && \
    echo ${USERNAME} ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/${USERNAME} && \
    chmod 0440 /etc/sudoers.d/${USERNAME} && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
