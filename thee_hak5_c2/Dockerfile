FROM alpine:latest

WORKDIR /app
ARG version=2.2.0

RUN apk add ca-certificates curl unzip libc6-compat
RUN wget https://downloads.hak5.org/api/devices/cloudc2-community/firmwares/${version} --no-cache \ 
    && unzip ${version} \
    && chmod +x /app/*

COPY start.sh /app

EXPOSE 8080 2022

CMD /bin/ash /app/start.sh