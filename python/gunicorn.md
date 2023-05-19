# Gunicorn

Gunicorn is a WSGI server for Python. It's helpful for production deployments of Flask applications and can speed things up like serving static files. Obviously the Flask development server only handles one connection at a time so that's a no-go for production.

It's easy to add multiple workers (see the `-w` switch).

It can also be configured to handle HTTPS connections with some command-line arguments.

You can get it to specify access logs using `--access-logfile`.

## Reloading

There is a `--reload` switch which functions as a watch flag. However don't do that in production.
Instead you can use the `HUP` signal (as documented [here](https://docs.gunicorn.org/en/stable/signals.html)). Send it to the master process (for finding that, you can run the command below).

```
ps -C gunicorn fc -o ppid,pid,cmd
```

This shows the parent/child relationship between the various gunicorn processes.

