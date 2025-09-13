FROM n8nio/n8n:latest

USER root

RUN echo "https://mirrors.aliyun.com/alpine/v3.22/main" > /etc/apk/repositories && \
echo "https://mirrors.aliyun.com/alpine/v3.22/community" >> /etc/apk/repositories

RUN apk update && apk upgrade && apk add --no-cache ffmpeg curl 

RUN apk update && apk upgrade && apk add --no-cache \
    chromium \
    nss \
    glib \
    freetype \
    freetype-dev \
    harfbuzz \
    ca-certificates \
    ttf-freefont \
    udev \
    ttf-liberation \
    font-noto-emoji \
    font-noto \
    font-noto-cjk


ENV PLAYWRIGHT_SKIP_BROWSER_DOWNLOAD=1 \
    PLAYWRIGHT_EXECUTABLE_PATH=/usr/bin/chromium-browser

RUN fc-cache -f -v

USER node
