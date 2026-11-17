FROM debian:bookworm-slim

ENV DEBIAN_FRONTEND=noninteractive

RUN dpkg --add-architecture i386 \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates curl lib32gcc-s1 lib32stdc++6 libc6:i386 tar unzip \
    && mkdir -p /opt/steamcmd \
    && curl -fSL "https://akamaihd.net" -o /tmp/steamcmd.tar.gz \
    && tar -xzvf /tmp/steamcmd.tar.gz -C /opt/steamcmd \
    && rm -f /tmp/steamcmd.tar.gz \
    && chmod +x /opt/steamcmd/steamcmd.sh /opt/steamcmd/linux32/steamcmd \
    && printf '#!/bin/sh\nexec /opt/steamcmd/steamcmd.sh "$@"\n' > /usr/local/bin/steamcmd \
    && chmod +x /usr/local/bin/steamcmd \
    && /opt/steamcmd/steamcmd.sh +quit || true \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /data
