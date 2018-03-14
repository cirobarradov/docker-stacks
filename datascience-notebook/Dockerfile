# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
FROM jupyter/scipy-notebook

LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

USER root
ENV LIBRDKAFKA_VERSION 0.9.1

RUN curl -Lk -o /opt/librdkafka-${LIBRDKAFKA_VERSION}.tar.gz https://github.com/edenhill/librdkafka/archive/${LIBRDKAFKA_VERSION}.tar.gz && \
    tar -xzf /opt/librdkafka-${LIBRDKAFKA_VERSION}.tar.gz -C /opt && \
    cd /opt/librdkafka-${LIBRDKAFKA_VERSION} && \
    ./configure && make && make install && make clean && ./configure --clean

USER $NB_UID
