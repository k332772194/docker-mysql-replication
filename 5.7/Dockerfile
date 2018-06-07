FROM mysql:5.7

# Default Replica ENV Variable 
ENV MYSQL_REPLICA_USER replication
ENV MYSQL_REPLICA_PASS pass

ENV MYSQL_MASTER_SERVER master
ENV MYSQL_MASTER_PORT 3306
ENV MYSQL_MASTER_WAIT_TIME 10

ENV MYSQL_REPLICA_SERVER_ID 0
ENV READ_ONLY 0

# Convert To MySQL ENV Variable 
ENV server_id $MYSQL_REPLICA_SERVER_ID
ENV read_only $READ_ONLY
ENV log_bin mysql-bin

COPY replica.sh /docker-entrypoint-initdb.d/
