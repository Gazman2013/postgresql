# postgresql
apt update
apt install postgresql-10;
apt install postgresql postgresql-contrib;
apt install pg-activity;
git clone https://github.com/pthom/northwind_psql.git;
apt install mc;
apt install net-tools;
su postgres;
cd /home;
mkdir backup;
chmod 777 backup;
psql -d maximdb -f /home/northwind_psql/northwind.sql;
pg_dump maximdb > /home/rodionov_gazman2013/backup/maximdb.sql;


