docker exec -i deploy-db-1 psql -U postgres -d stream_call < streamcall_dump.sql

docker exec -i deploy-db-1 psql -U postgres
drop database stream_call
create database stream_call;

sudo service postgresql stop
