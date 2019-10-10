usuario@ubuntu:~$ sudo passwd postgres
Introduzca la nueva contraseña de UNIX:
Vuelva a escribir la nueva contraseña de UNIX:
passwd: contraseña actualizada correctamente
usuario@ubuntu:~$ sudo su postgres
postgres@ubuntu:/home/usuario$ psql
could not change directory to "/home/usuario": Permiso denegado
psql (10.10 (Ubuntu 10.10-0ubuntu0.18.04.1))
Type "help" for help.

postgres=# CREATE USER miusuario;
ERROR:  role "miusuario" already exists
postgres=#
ALTER ROLE miusuario WITH PASSWORD 'mipassword';
ALTER ROLE
postgres=# CREATE DATABASE pract1;
CREATE DATABASE
postgres=# create table usuarios (
postgres(# nombre varchar(30),
postgres(# clave varchar(10)
postgres(# );
CREATE TABLE
postgres=# insert into usuarios (nombre, clave) values ('Isa', 'asdf');
INSERT 0 1
postgres=# insert into usuarios (nombre, clave) values ('Pablo', 'jfx344');
INSERT 0 1
postgres=# insert into usuarios (nombre, clave) values ('Ana', 'tru3fal');
INSERT 0 1
postgres=# |dt
postgres-# \dt
          List of relations
 Schema |   Name   | Type  |  Owner
--------+----------+-------+----------
 public | usuarios | table | postgres
(1 row)

postgres-# SELECT *
postgres-# FROM usuarios;
ERROR:  syntax error at or near "|"
LINE 1: |dt
        ^
postgres=# ;
postgres=# SELECT *
FROM usuarios;
 nombre |  clave
--------+---------
 Isa    | asdf
 Pablo  | jfx344
 Ana    | tru3fal
(3 rows)

postgres=# \s

postgres=# \q
postgres@ubuntu:/home/usuario$ exit
exit
usuario@ubuntu:~$
