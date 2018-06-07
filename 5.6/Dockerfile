FROM mysql:5.6

# Default Replica ENV Variable 
ENV MYSQL_REPLICA_USER replication
ENV MYSQL_REPLICA_PASS pass

# For version compatible
RUN echo '[mysqld]\nlog_bin=mysql-bin\n' > /etc/mysql/conf.d/replica_custom.cnf

COPY replica.sh /docker-entrypoint-initdb.d/
