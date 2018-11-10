FROM alpine:latest

RUN apk add --update mysql mysql-client \
    #&& apk add dos2unix \
    && rm -f /var/cache/apk/*

COPY startup.sh /startup.sh
#RUN dos2unix /startup.sh

COPY my.cnf /etc/mysql/my.cnf

EXPOSE 3306

CMD ["/startup.sh"]