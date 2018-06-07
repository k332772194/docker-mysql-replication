FROM mysql:8.0

# Default Replica ENV Variable 
ENV MYSQL_REPLICA_USER replication
ENV MYSQL_REPLICA_PASS pass

# For version compatible
RUN echo -e '[mysqld]\nlog_bin=mysql-bin\n' > /etc/mysql/conf.d/replica_custom.cnf

COPY replica.sh /docker-entrypoint-initdb.d/
