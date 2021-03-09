Репликация

1. master and slave postgresql 12.6
2. Master settings postgresql.conf, pg_hba.conf, create database, create role 
3. Slave create recovery.conf
4. Master create new table, insert values 
5. master
6. \c levelup
You are now connected to database "levelup" as user "postgres".
7. levelup=# CREATE TABLE replicatest (test varchar(100));
CREATE TABLE
8. levelup=# INSERT INTO replicatest VALUES ('test string');
INSERT 0 1

9. postgres=# \c levelup
You are now connected to database "levelup" as user "postgres".
levelup=# select * from replicatest;
     test     

 test string
 test strin1g
 test strin2g
 test strin3g
(4 rows)

10. . test reprication 

slave
11. \c levelup
You are now connected to database "levelup" as user "postgres".
levelup=# select * from replicatest;
     test     

 test string
 test strin1g
 test strin2g
 test strin3g
(4 rows)

