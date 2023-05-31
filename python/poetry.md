# About

Poetry is another way to manage dependencies in python.
The main feature is that `poetry add` will update the `poetry.lock` file (while `pip install` does not).

To generate a requirements file for pip, do this:

```
poetry export --without-hashes --format=requirements.txt > requirements.txt
```

## add to dev dependency

Use the `-D` switch, or `--group dev`

## install dev dependencies

```
poetry install --with dev
```

