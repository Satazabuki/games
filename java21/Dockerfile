FROM eclipse-temurin:21-jre-jammy

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates curl git jq tar unzip tini \
    && useradd -d /home/container -m container \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /data
