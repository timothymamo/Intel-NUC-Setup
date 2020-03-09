FROM alpine:latest

RUN apk add --no-cache curl bash bind-tools

COPY update.sh /

WORKDIR /

CMD ["/bin/sh", "/update.sh"]
