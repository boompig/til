# Postgres

## Constraints

You cannot modify a constraint except to enable/disable it. You must drop it and create a new one (for example to add `ON DELETE CASCADE`).

You can enforce that a column's value is one of a few allowed options:

```
ALTER TABLE <table>
ADD CONSTRAINT chk_val CHECK (col in ('yes','no','maybe'))
```

## Statement-Level Logging

You can enable statement-level logging. Various options are documented [here](https://stackoverflow.com/a/8208945/755934).
The relevant files on a Mac are documented [on the Postgres.App website](https://postgresapp.com/documentation/configuration-general.html).



## Statement Timeouts

There is an easy way to set up per-statement timeouts for a given database.

```
set statement_timeout to 60000;
```

Note that the time is in milliseconds.

You can then view the timeout with this query:

```
show statement_timeout;
```

See [the docs](https://www.postgresql.org/docs/13/runtime-config-client.html)


## Version

You can get the server's version with this query:

```
show server_version;
```
