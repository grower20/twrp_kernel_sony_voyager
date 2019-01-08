FROM debian:stretch

ENV DEBIAN_FRONTEND=noninteractive \
    CROSS_COMPILER_REPO=https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9 \
    CROSS_COMPILER_DIRNAME=aarch64-linux-android

# install git
RUN apt update && \
    apt install -y git

# install cross compiler and build tools
RUN cd / && \
    apt update && \
    apt install -y build-essential python && \
    git clone $CROSS_COMPILER_REPO && \
    ln -s ${CROSS_COMPILER_DIRNAME}* $CROSS_COMPILER_DIRNAME

# set cross compile environment
ENV CROSS_COMPILE="${CROSS_COMPILER_DIRNAME}-" \
    ARCH=arm64 \
    PATH="/${CROSS_COMPILER_DIRNAME}/bin:${PATH}"
