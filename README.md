Репликация

1. master and slave postgresql 12.6
2. Master settings postgresql.conf, pg_hba.conf, create database, create role 
3. Slave create recovery.conf
4. Master create new table, insert values 
--------------------------------------------------------
master
\c levelup
You are now connected to database "levelup" as user "postgres".
levelup=# CREATE TABLE replicatest (test varchar(100));
CREATE TABLE
levelup=# INSERT INTO replicatest VALUES ('test string');
INSERT 0 1
levelup=# INSERT INTO replicatest VALUES ('test strin1g');
INSERT 0 1
levelup=# INSERT INTO replicatest VALUES ('test strin2g');
INSERT 0 1
levelup=# INSERT INTO replicatest VALUES ('test strin3g');
INSERT 0 1
levelup=# \q
postgres@instance-1:/root$ psql
could not change directory to "/root": Permission denied
psql (12.6 (Ubuntu 12.6-0ubuntu0.20.04.1))
Type "help" for help.

postgres=# \c levelup
You are now connected to database "levelup" as user "postgres".
levelup=# select * from replicatest;
     test     
--------------
 test string
 test strin1g
 test strin2g
 test strin3g
(4 rows)
----------------------------------------------
5. test reprication 
---------------------------------------------
slave
\c levelup
You are now connected to database "levelup" as user "postgres".
levelup=# select * from replicatest;
     test     
--------------
 test string
 test strin1g
 test strin2g
 test strin3g
(4 rows)
----------------------------------------------
