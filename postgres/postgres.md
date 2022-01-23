# Postgres

You cannot modify a constraint except to enable/disable it. You must drop it and create a new one (for example to add `ON DELETE CASCADE`).

You can enable statement-level logging. Various options are documented [here](https://stackoverflow.com/a/8208945/755934).
The relevant files on a Mac are documented [on the Postgres.App website](https://postgresapp.com/documentation/configuration-general.html).
