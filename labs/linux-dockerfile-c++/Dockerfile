FROM ubuntu:22.04
ENV DEBIAN_FRONTEND=noninteractive
WORKDIR /home/project

# General utilities
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
        net-tools iputils-ping sudo wget vim nano ca-certificates && \
    rm -rf /var/lib/apt/lists/*

# C++ build toolchain: gcc/g++ (gcc-11), make, cmake, git, python3 + pip
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
        build-essential cmake git python3 python3-pip python3-dev && \
    rm -rf /var/lib/apt/lists/*

# Conan 2.x — modern C/C++ package manager
RUN pip3 install --no-cache-dir conan && \
    conan profile detect --force && \
    conan profile show

# Container starts with Bash
CMD ["bash"]
