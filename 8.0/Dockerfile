FROM mysql:8.0

# Default Replica ENV Variable 
ENV MYSQL_REPLICA_USER replication
ENV MYSQL_REPLICA_PASS pass

ENV MYSQL_MASTER_SERVER master
ENV MYSQL_MASTER_PORT 3306
ENV MYSQL_MASTER_WAIT_TIME 10

ENV log_bin mysql-bin

COPY replica.sh /docker-entrypoint-initdb.d/
