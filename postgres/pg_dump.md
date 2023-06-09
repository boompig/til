Today I learned about `pg_dump`. The `pg_dump` command can be used to create a text-only or binary dump of your Postgres database.

You can use it with the `--schema-only` option to just dump the schema without fetching any of the data (`--no-acl --no-owner` options are helpful here).

By default `pg_dump` will dump in text mode but you can specify a binary mode with `-Fc`.

You can then restore a dump (for example to migrate a database) in this way:

```
pg_restore <file> -d <dbname> --user <username> -h <hostname> 
```
