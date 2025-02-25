latest version from PPA

```shell
sudo apt install postgresql
```
---

## Alter user 'postgres' pasword
---
1.  change to 'postgres' user
2. connect to psql
3. alter user password

```shell
sudo -i -u postgres
psql
```

inside psql:
```sql
ALTER USER postgres WITH PASSWORD 'postgres';
```

exit from psql and postgres:
```shell
\q
exit
```
---

## Install pgAdmin4 - desktop mode only
---
latest version from https://www.pgadmin.org/download/pgadmin-4-apt/

1. add public key
```shell
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```

2. create config repository 
```shell
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```

1. install desktop mode only
```shell
sudo apt install pgadmin4-desktop
```
