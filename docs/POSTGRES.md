# All Things Postgres

## Dump and Restore Databases from Remote Instances

``` bash
pg_dump -h localhost -p 5454 -U postgres -f dump.sql database_name

psql -f dump.sql database_name
```

