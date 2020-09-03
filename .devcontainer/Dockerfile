ARG VARIANT=buster
FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

WORKDIR /work

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install python3 python3-pip git mercurial

RUN python3 -m pip install mbed-cli

RUN wget -qO- https://developer.arm.com/-/media/Files/downloads/gnu-rm/9-2019q4/gcc-arm-none-eabi-9-2019-q4-major-x86_64-linux.tar.bz2 | tar -xj
#ENV PATH $PATH:/work/gcc-arm-none-eabi-9-2019-q4-major/bin
#RUN mbed config -G GCC_ARM_PATH "/work/gcc-arm-none-eabi-9-2019-q4-major/bin"
ENV MBED_GCC_ARM_PATH /work/gcc-arm-none-eabi-9-2019-q4-major/bin
