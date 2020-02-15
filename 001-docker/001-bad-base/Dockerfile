FROM ubuntu:xenial

# install dependencies
RUN apt-get update && \
    apt-get -y install curl tar gzip

# create directory
RUN mkdir -p /data/jdk

# download java
RUN curl -sf  -o /data/jdk/openjdk.tar.gz -L https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u242-b08/OpenJDK8U-jdk_x64_linux_hotspot_8u242b08.tar.gz

# extract java
RUN cd /data/jdk && tar xzvf ./openjdk.tar.gz

# create link
RUN ln -s /data/jdk/jdk8u242-b08 /data/jdk/jdk8

# remove directory
RUN rm /data/jdk/openjdk.tar.gz

# export java_home for future use cases
ENV JAVA_HOME=/data/jdk/jdk



