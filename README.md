# MariaDB-solution
MariaDB is an open source database forked from MySQL.
### How it works

The server is launched on containerum.com, so you can connect to it using any data management tool, e.g. Valentina Studio.

### It consists of:

* Maria DB

To launch this solution on Containerum.com sign up with the service, download and use [Containerum CLI](https://github.com/containerum/chkit) `chkit`.

1. Run the Solution with `chkit solution`:
```
chkit solution run containerum/MariaDB-solution -e NAME=maria-db -e USER=maria -e PASS=12345678
```

2. Make sure that the Solution is running:

```
$ chkit get deploy
+----------------+------+-------------+------+-------+-----+
|      NAME      | PODS | PODS ACTIVE | CPU  |  RAM  | AGE |
+----------------+------+-------------+------+-------+-----+
| maria-db-0scpq |    1 |           1 | 500m | 512Mi | 9m  |
+----------------+------+-------------+------+-------+-----+
```
3. Using `chkit get` get the address and the port to access the running Solution:
```
$ chkit get svc
+----------------+----------------+----------+-------------------+-----------------+-----+
|      NAME      |   CLUSTER-IP   | EXTERNAL |       HOST        |      PORTS      | AGE |
+----------------+----------------+----------+-------------------+-----------------+-----+
| maria-db-0scpq | 10.107.136.66  | true     | x2.containerum.io | 11056:3306/TCP  | 5s  |
+----------------+----------------+----------+-------------------+-----------------+-----+
```
4. Open your data management tool, e.g. Valentina Studio, and connect to `x2.containerum.io:11056`- now you can create or manage your DB.
