# Flask

If you register API handlers in blueprints using the following:

App.py

```
app.register_blueprint('/api/foo', foo_api)
```

Foo.py

```
@foo_api.route('/')
```

This structure will automatically redirect any requests to `/api/foo` to `/api/foo/`.
This is really annoying.
If you don't want that, change Foo.py to this:

```
@foo_api.route('/')
@foo_api.route('')
```

Which will handle both the regular and trailing-slash case.

