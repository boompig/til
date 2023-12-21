# Gotchas

SQLAlchemy is a useful package to provide an ORM on top of the database of choice (e.g. Postgresql, SQLite).
However, the ORM leaves some things opaque, such as what is handled at the application level and what is handled at the database level.
This can be annoying when you want to copy a database together with its schema, and find that the schema doesn't match what you thought it did.

1. The `default` keyword works at the python level, not at the SQL level. To get the same behaviour at the SQL level, use [`server_default`](https://docs.sqlalchemy.org/en/14/core/metadata.html#sqlalchemy.schema.Column.params.server_default).

## Small Tips

- `joinedload` avoids the N + 1 problem, can specify with `.options` as part of query
- you can use `db.session.expire` to manually expire a mapped object and force a refetch on the next query

