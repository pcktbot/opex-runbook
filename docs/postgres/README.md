# All Things Postgres

## Postgres CLI

MacOS using [PostgresApp](https://postgresapp.com/documentation/cli-tools.html) will need to add commands to shell path. Run the following (requires admin user):

``` sh
sudo mkdir -p /etc/paths.d && echo /Applications/Postgres.app/Contents/Versions/latest/bin | sudo tee /etc/paths.d/postgresapp
```

## Dump and Restore Databases from Remote Instances

Dump backup of `database_name` from Postgres instance.

``` sh
pg_dump -h localhost -p 5454 -U postgres -f dump.sql database_name
```

> You will be prompted for the password.

- `-f` is the output file name.
- `-h` is the host (alias, IP, or domain name).
- `-p` is the TCP port. Postgres' default is `5432`.
- `-U` is the database user. Default is `postgres`.
- last is the `database_name`.

Restore `database_name` from dump file.

``` sh
psql -f dump.sql database_name
```


