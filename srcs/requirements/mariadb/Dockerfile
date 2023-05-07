FROM alpine:3.16

RUN apk update && apk add mariadb mariadb-client --no-cache
RUN mysql_install_db --user=mysql --datadir=/var/lib/mysql

COPY conf/my.cnf /etc/mysql/my.cnf
COPY tools/mysql.sh .

RUN  sh mysql.sh && rm mysql.sh

USER mysql

EXPOSE 3306
