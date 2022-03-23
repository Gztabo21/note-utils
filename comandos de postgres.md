# Postgresql - notaciones - Comandos
 

## Instalar PostgresSQL - Linux
1 ```sudo apt update```

2 ```sudo apt install postgresql postgresql-contrib```

3 acceder con ```sudo -i -u postgres```.

4  crea un nuevo usuario ```createuser --interactive```, colocaras el nombre.
```Enter name of role to add: usernew Shall the new role be a superuser? (y/n) y```

5 para cambiar contraseña:
```\password```
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

