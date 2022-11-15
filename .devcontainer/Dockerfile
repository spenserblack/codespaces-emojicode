ARG VARIANT="bullseye"
FROM mcr.microsoft.com/devcontainers/base:${VARIANT}
RUN apt update \
    && apt install -y g++ libncurses5 wget \
    && wget -O emojicode.tar.gz https://github.com/emojicode/emojicode/releases/download/v1.0-beta.2/Emojicode-1.0-beta.2-Linux-x86_64.tar.gz \
    && tar xzf emojicode.tar.gz \
    && rm emojicode.tar.gz \
    && cp ./Emojicode-1.0-beta.2-Linux-x86_64/emojicodec /usr/bin/emojicodec \
    && chmod 755 /usr/bin/emojicodec \
    && rsync -rl ./Emojicode-1.0-beta.2-Linux-x86_64/packages/ /usr/local/EmojicodePackages \
    && rsync -rl ./Emojicode-1.0-beta.2-Linux-x86_64/include /usr/local/include/emojicode \
    && chmod -R 755 /usr/local/include/emojicode \
    && rm -rf ./Emojicode-1.0-beta.2-Linux-x86_64 \
    && apt remove -y wget
