## LAB-07: Creating Docker Container to Build C++ on Ubuntu 22.04

- In this scenario, we'll create a Dockerfile from scratch that includes CMake, Git, Python3, Conan and GCC.
- **Dockerfile**: https://github.com/omerbsezer/Fast-Docker/blob/main/labs/linux-dockerfile-c%2B%2B/Dockerfile
- Create a Dockerfile that includes the following content:

> **2024/2025 update:** modernized to **Ubuntu 22.04 LTS**. GCC (gcc-11) and CMake now come straight from the distribution (no PPA, no source build), and Conan is installed at its current 2.x version with `conan profile detect`. Apt lists are cleaned in each layer to keep the image small — the hygiene practices taught in LAB 11/12.

```
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
```

- Create directory on your C: (e.g. C:\Linux-Project), this directory is used for sharing file between container and host PC.

- Run following command to create Ubuntu environment, it creates 'build-env-ubuntu18' Docker image: 

```
docker image build -t build-env-ubuntu18 .
```

- Run following command to create container from 'build-env-ubuntu18' image, bind mount to 'C:\Linux-Project' directory. Create directory before run: C:\Linux-Project. Copy the project into the C:\Linux-Project.

```
docker container run -it --name con-linux -v C:\Linux-Project:/home/project build-env-ubuntu18 /bin/bash
```

- Go to your to build project (-S: source project path, -B: build project path)

```
cd ProjectName/source
sudo cmake -S /home/project/ProjectName/source -B /home/project/ProjectName/build 
```

- Then go to the build:
```
cd ..
cd build
make -j4
```





