FROM alpine:3.17

RUN apk update --no-cache \ 
    && apk upgrade --no-cache \
	&& apk add --no-cache mysql \ 
			              mysql-client 

COPY conf/mariadb-server.cnf /etc/my.cnf.d/mariadb-server.cnf
COPY conf/entrypoint.sh /entrypoint.sh

EXPOSE 3306

ENTRYPOINT [ "/entrypoint.sh" ]

CMD ["mysqld", "--user=mysql"]
