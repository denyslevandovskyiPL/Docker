FROM alpine:latest AS client

RUN apk update && apk upgrade --no-cache

WORKDIR /home

CMD ["sh", "server.sh" ]
