FROM alpine

RUN apk add --no-cache mysql-client
CMD [ "/usr/sbin/crond", "-f", "-d8" ]
