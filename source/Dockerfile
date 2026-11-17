FROM debian:bookworm-slim

ENV DEBIAN_FRONTEND=noninteractive

RUN dpkg --add-architecture i386 \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates curl gdb iproute2 lib32gcc-s1 lib32stdc++6 \
        libc6:i386 libsdl2-2.0-0:i386 libstdc++6:i386 locales tar unzip tini \
    && useradd -d /home/container -m container \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /data
