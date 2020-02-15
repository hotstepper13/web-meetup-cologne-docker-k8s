FROM ubuntu:xenial

# install dependencies
RUN apt-get update && \
    apt-get -y install curl tar gzip && \
    mkdir -p /data/jdk && \
    curl -sf  -o /data/jdk/openjdk.tar.gz -L https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u242-b08/OpenJDK8U-jdk_x64_linux_hotspot_8u242b08.tar.gz && \
    cd /data/jdk && tar xzvf ./openjdk.tar.gz && \
    ln -s /data/jdk/jdk8u242-b08 /data/jdk/jdk8 && \
    rm /data/jdk/openjdk.tar.gz && \
    apt-get clean autoclean && \
    apt-get autoremove --yes && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/

# export java_home for future use cases
ENV JAVA_HOME=/data/jdk/jdk



