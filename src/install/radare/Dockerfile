FROM ubuntu:bionic
MAINTAINER Johannes vom Dorp <johannes.vom.dorp@fkie.fraunhofer.de>

ARG HTTP_PROXY
ARG HTTPS_PROXY
ARG http_proxy
ARG https_proxy
ARG NO_PROXY
ARG no_proxy

RUN apt-get update && apt-get install -y \
    make gcc npm \
    python3-pip git sudo \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /opt/app

COPY install.sh /opt/app/install.sh

RUN /opt/app/install.sh

WORKDIR /opt/app/fact_radare_viewer

CMD ["python3", "src/serve.py"]
