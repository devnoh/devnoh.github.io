# POSTGRES

## Install

* install the binary
$ brew install postgresql

* init db
$ initdb /usr/local/var/postgres

* start the postgres server
$ postgres -D /usr/local/var/postgres

* create your database
$ createdb mydb

## Create User

* Create user with password
$ createuser -P myusername

* Grant rights for just created user to database
$ psql mydb

* after connecting
mydb=# GRANT ALL PRIVILEGES ON database mydb TO myusername;
mydb=# GRANT ALL PRIVILEGES ON database postgres TO myusername;

* drop database
$ cropdb mydb
