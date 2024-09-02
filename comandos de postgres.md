# Postgresql - notaciones - Comandos
 

## Instalar PostgresSQL - Linux
1 ```sudo apt update```

2 ```sudo apt install postgresql postgresql-contrib```

3 acceder con ```sudo -i -u postgres```.

4  crea un nuevo usuario ```createuser --interactive```, colocaras el nombre.
```Enter name of role to add: usernew Shall the new role be a superuser? (y/n) y```

5 colocar en la termina :
```psql``` luego dar enter


6 para cambiar contraseña:
```\password <username>```

## Crear Basedatos

```CREATE DATABASE nuevadb;```
## Habilita el localhost

1.- escribe en la terminal ```sudo nano /etc/postgresql/[version]/main/postgresql.conf``` 

2.-  descomenta la siguente linea de codigo  ``` listen_addresses = "localhost"``` 
3 luego reinicia con algunos de estos comandos.
 ``` sudo /etc/init.d/postgresql restart```   o  ``` sudo service postgresql restart``` 

## Exportar la DDBB por postgres
 psql -U username -d dbname < filename.sql

-- For Postgres versions 9.0 or earlier
psql -U username -d dbname -1 -f filename.sql

or

pg_restore -U username -d dbname -1 filename.dump 
## Importar DDBB en postgress
```
psql -U postgres -d [Nombre_Base_De_Datos] < [Nombre_Base_De_Datos].sql
```
## Lista de comando de terminal DATABASES PSQL

/l listas de databases,
## Remove _sql_constraints
you could remove it using psql command. for example if you have the following constraint

_sql_constraints = [
    ('phone_company_unique', 'unique(type,phone)', 'The phone unique among companies!')
]
you could use:

ALTER TABLE res_partner DROP CONSTRAINT res_company_phone_company_unique;
