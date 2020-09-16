# MYSQL Documentation


**Step 1:** Pull image dari [Docker HUB Mysql](https://hub.docker.com/_/mysql)
```bash
docker pull mysql
```
\
**Step 2:** Buat Container mysql dan Set Passwordnya
```bash
docker run --name nama-containernya -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag
```
**nama-containernya** = nama containernya sesuai yang diinginkan\
**my-secret-pw** = buat password untuk akses mysql\
**tag** = ganti menjadi **latest** untuk version terakhir

\
**Step 3:** Buat Container mysql dan Set Passwordnya
```bash
docker exec -it some-mysql mysql -u root -p
```

lalu masukan password yang  dibuat pada ***MYSQL_ROOT_PASSWORD***
```bash
Enter password:
```

setelah sukses akan muncul tampilan seperti ini
```bash
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.21 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
```
\
untuk check database nya, menggunakan perintah berikut
```mysql
show databases;
```
outputnya:
```mysql
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.01 sec)
```
\
lalu untuk create database nya:

```mysql
CREATE DATABASE nama_databasenya;
```
outputnya:
```mysql
Query OK, 1 row affected (0.02 sec)
```

\
**Step 4:** Buat Networknya
```bash
docker network create nama-networknya
```

contoh hasil outputnya:
```bash
1ef833a4aed62361ca1f2053bc7cd0cd4a0f3971a041bc87a85aedbddafcc3ee
```

**Step 5:** Check Networknya
```bash
docker network ls
```
\
contoh outputnya:
```bash
NETWORK ID          NAME                DRIVER              SCOPE
487f2e83e4d7        bridge              bridge              local
20c07d3253a0        host                host                local
1ef833a4aed6        nama-networknya     bridge              local
c303de725330        none                null                local
```


**Step 6:** Connect a container to a network
```bash
docker network connect nama-networknya nama-containernya
```