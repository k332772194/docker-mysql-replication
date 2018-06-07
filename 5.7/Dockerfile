FROM mysql:5.7

# For version compatible
RUN echo '[mysqld]\nlog_bin=mysql-bin\n' > /etc/mysql/conf.d/replica_custom.cnf

COPY replica.sh /docker-entrypoint-initdb.d/
