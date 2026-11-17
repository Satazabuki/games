FROM debian:bookworm-slim

ENV DEBIAN_FRONTEND=noninteractive

RUN dpkg --add-architecture i386 \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates curl lib32gcc-s1 lib32stdc++6 libc6:i386 tar unzip \
    && mkdir -p /opt/steamcmd \
    && curl -sqL "https://akamaihd.net" | tar zxvf - -C /opt/steamcmd \
    && ln -s /opt/steamcmd/steamcmd.sh /usr/local/bin/steamcmd \
    && /opt/steamcmd/steamcmd.sh +quit || true \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /data
