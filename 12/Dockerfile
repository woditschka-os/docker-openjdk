FROM quay.io/woditschka/centos:7

ARG OPENJDK_VERSION=12
ARG OPENJDK_BUILD=11
ARG OPENJDK_TGZ=openjdk-${OPENJDK_VERSION}-ea+${OPENJDK_BUILD}_linux-x64_bin.tar.gz
ARG OPENJDK_URL=https://download.java.net/java/early_access/jdk${OPENJDK_VERSION}/${OPENJDK_BUILD}/GPL/${OPENJDK_TGZ}

ENV JAVA_HOME /usr/lib/jvm/java

RUN yum update -y && \
    yum -y install wget && \
    yum clean all && \
    rm -rf /var/cache/yum && \
    mkdir -p /usr/lib/jvm && \
    cd /usr/lib/jvm && \
    curl ${OPENJDK_URL} --output ${OPENJDK_TGZ} && \
    tar -xzf ${OPENJDK_TGZ} && \
    rm -f ${OPENJDK_TGZ} && \
    ln -s jdk-${OPENJDK_VERSION} java && \
    alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-${OPENJDK_VERSION}/bin/java 2