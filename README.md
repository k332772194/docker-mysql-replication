# MySQL Replication Docker Image
This image is based on [Offcial MySQL Docker Image](https://hub.docker.com/_/mysql/) with replication supported out of box.
Some script copy/modify from [Project mysql-replica](https://github.com/twang2218/mysql-replica)

# Basic Usage

* Master
```shell
docker run
-p 3306
--env MYSQL_ROOT_PASSWORD=root_pass
--detach
coder4/mysql-replication:8.0
```

* Slave
```shell
docker run
-p 3306
--env MYSQL_ROOT_PASSWORD=root_pass
--env MYSQL_MASTER_SERVER=master
--env MYSQL_REPLICA_SERVER_ID=1
--env READ_ONLY=1
--detach
coder4/mysql-replication:8.0
```

# All Extra Environment Variable Add By Our Image
* MYSQL_REPLICA_USER
 * default replication
 * please keep same for master/slave
* MYSQL_REPLICA_PASS
 * default pass
 * please keep same for master/slave
* MYSQL_MASTER_HOST
 * default master
 * only valid for slave 
* MYSQL_MASTER_PORT
 * default 3306
 * only valid for slave 
* MYSQL_MASTER_WAIT_TIME
 * default 10
 * only valid for slave
* MYSQL_REPLICA_SERVER_ID: 
 * master default set to 0, please don't change
 * slave must set different value other than 0
* READ_ONLY
 * default 0
 * master should not set
 * slave recommand set to 1
