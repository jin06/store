# Use an official TinyGo image as base (or build from Golang)
FROM tinygo/tinygo:0.30.0

USER root

# Install WASI SDK (includes wasi-libc)
RUN apt-get update && apt-get install -y \
    curl \
    build-essential \
    clang \
    make \
    cmake \
    git \
    llvm \
    wget \
    && apt-get clean

RUN wget https://github.com/WebAssembly/wasi-sdk/releases/download/wasi-sdk-20/wasi-sdk-20.0-linux.tar.gz \
    && tar -xvzf wasi-sdk-20.0-linux.tar.gz \
    && mv wasi-sdk-20.0 /opt/wasi-sdk

# Set environment variables
ENV WASI_SDK_PATH=/opt/wasi-sdk/share/wasi-sysroot
ENV PATH=$PATH:/opt/wasi-sdk/bin

# Set default working directory
WORKDIR /workspace

# Entry point for direct execution
CMD ["tinygo", "version"]