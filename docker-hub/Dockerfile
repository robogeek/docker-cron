FROM alpine

RUN apk add --no-cache mysql-client less gzip rsync
CMD [ "/usr/sbin/crond", "-f" ]
