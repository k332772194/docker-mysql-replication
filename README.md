# MySQL Replication Docker Image
This image is based on [Offcial MySQL Docker Image](https://hub.docker.com/_/mysql/) with replication supported out of box.
Some script copy/modify from [Project mysql-replica](https://github.com/twang2218/mysql-replica)

# Basic Usage

* Master
```shell
docker run \
-p 3306 \
--env MYSQL_ROOT_PASSWORD=root_pass \
--detach \
coder4/mysql-replication:8.0 --server-id=1
```

* Slave
```shell
docker run \
-p 3306 \
--env MYSQL_ROOT_PASSWORD=root_pass \
--env MYSQL_MASTER_SERVER=master \
--detach \
coder4/mysql-replication:8.0 \
--server-id=2 --read-only=1
```

# All Extra Environment Variable Add By Our Image
* MYSQL_REPLICA_USER
  * default: replication
  * please keep same for master/slave
* MYSQL_REPLICA_PASS
  * default: pass
  * please keep same for master/slave
* MYSQL_MASTER_SERVER 
  * set means switch to slave mode
* MYSQL_MASTER_PORT
  * default: 3306
  * only valid for slave 
* MYSQL_MASTER_WAIT_TIME
  * default: 3
  * only valid for slave, if master not alive after time's seconds, slave would exit

# All Argument Variable
* --server-id: 
  * master should set to 1(for 8.0 compatible)
  * slave must set different value > 1
* --read-only
  * default 0
  * master should not set
  * slave recommand set to 1
