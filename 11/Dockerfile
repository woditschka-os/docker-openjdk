FROM quay.io/woditschka/centos:7

RUN yum update -y && \
    yum install -y java-11-openjdk-devel && \
    yum clean all && \
    rm -rf /var/cache/yum