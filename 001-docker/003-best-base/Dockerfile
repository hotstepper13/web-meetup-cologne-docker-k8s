FROM alpine:3.11

# install dependencies
RUN apk --no-cache add curl tar gzip && \
    mkdir -p /data/jdk && \
    echo "Downloading Java" && \
    curl -sf  -o /data/jdk/openjdk.tar.gz -L https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u242-b08/OpenJDK8U-jdk_x64_linux_hotspot_8u242b08.tar.gz && \
    cd /data/jdk && \
    tar xzvf ./openjdk.tar.gz && \
    ln -s /data/jdk/jdk8u242-b08 /data/jdk/jdk8 && \
    rm /data/jdk/openjdk.tar.gz && \
    apk del --purge curl tar gzip

# export java_home for future use cases
ENV JAVA_HOME=/data/jdk/jdk



