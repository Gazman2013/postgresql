# postgresql
apt update
apt install postgresql-10
apt install postgresql postgresql-contrib
apt install pg-activity
git clone https://github.com/pthom/northwind_psql.git
apt install mc
apt install net-tools
su postgres
cd /home
mkdir backup
chmod 777 backup
psql -d maximdb -f /home/northwind_psql/northwind.sql
pg_dump maximdb > /home/rodionov_gazman2013/backup/maximdb.sql
su postgres
psql
\l
connect maximdb
\dt
CREATE TABLE weather (
    city            varchar(80),
    temp_lo         int,           -- минимальная температура дня
    temp_hi         int,           -- максимальная температура дня
    prcp            real,          -- уровень осадков
    date            date
);
 public | weather                | table | postgres
 INSERT INTO weather VALUES ('San Francisco', 46, 50, 0.25, '1994-11-27');
  SELECT * FROM weather;
     city      | temp_lo | temp_hi | prcp |    date
---------------+---------+---------+------+------------
 San Francisco |      46 |      50 | 0.25 | 1994-11-27
(1 row)
DROP TABLE weather;
\dt
по новой CREATE TABLE weather NSERT INTO weather VALUES 

 

