# Postgres

## Escaping Quotes

You can escape quotes by doing the following:

```
UPDATE landlord_messages
SET contents='Hey what''s up'
WHERE uuid=:uuid;
```

Note the double `''`.

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

## Date Manipulation with intervals

If you have a column called `inserted_at` you can run this statement:

```
UPDATE landlord_messages
SET inserted_at=now() - interval '1 day'
WHERE uuid=:uuid;
```

Note the `interval` keyword.


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

## limiting updates to a single row

You can make sure your update only hits a single row using the `TOP` syntax. See [this question](https://stackoverflow.com/a/26929469/755934) for more info.

```
UPDATE TOP (1) table1 
SET name2 = '01' 
WHERE name1='xx'
```

## Scripts

To use variables in scripts, use the `\set` command. For example:

```
\set foo 3
\set bar 'hello world'
```

You can then reference the variable with the `:varname` syntax in queries. For example:

```
SELECT * FROM users WHERE id = :user_id;
```

There is some strangeness in these cases with string/quoted variables. To get around it, use this syntax:

```
UPDATE messages SET contents = :'msg_contents' WHERE user_id = :user_id;
```

Notice that the variable name is quoted while the colon appears before the quote.
