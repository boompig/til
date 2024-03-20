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

## `split_part`

Postgresql has a built-in function to split strings pairs called [split\_part](https://www.postgresql.org/docs/9.1/functions-string.html).
Example usage to get domains from email addresses:

```
SELECT email, split_part(email, '@', 2) AS domain FROM users;
```

## `make_interval`

Postgresql has a built-in function to make intervals using variables called [make\_interval](https://www.postgresql.org/docs/current/functions-datetime.html).
Example usage:

```
SELECT make_interval(days => 10);
```

Note that this can also be used with a variable in place of the 10.

## Updates with query rather than value

If you want to do a mass update, you can use an update-from statement such as the following:

```sql
UPDATE renter_leads
SET leasing_team_id=t.leasing_team_id
FROM (
    SELECT l.uuid AS lead_uuid, l.owner AS owner, u.leasing_team_id AS leasing_team_id
    FROM renter_leads AS l
    JOIN users AS u ON l.owner=u.id
    WHERE l.leasing_team_id IS NULL
) AS t
WHERE t.lead_uuid=renter_leads.uuid
AND renter_leads.leasing_team_id IS NULL;
```
