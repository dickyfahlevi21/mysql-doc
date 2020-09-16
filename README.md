# MYSQL Documentation


**Step 1:** Pull image dari [Docker HUB Mysql](https://hub.docker.com/_/mysql)
```bash
docker pull mysql
```
\
**Step 2:** Buat Container mysql dan Set Passwordnya
```bash
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag
```
**some-mysql** = nama containernya\
**my-secret-pw** = buat password untuk akses mysql

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
**Step 4:** 
```bash

```