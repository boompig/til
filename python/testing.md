# Pytest

Individual tests can be selected with the `-k` switch

Usually you want to specify `-x`: stop after first failed test

You can ignore deprecation warnings specifically with `-W ignore::DeprecationWarning`. You can also specify specifically what warning to ignore in a pytest.ini file.
[Read this question](https://stackoverflow.com/a/53218641/755934) for more tips regarding handling warnings.

## Output Capture

Normally when all tests pass, there is no output.
This can be annoying when trying to collect metrics.

To disable output capture, use the `-s` switch.

## Verifying exceptions are raised

Use `pytest.raises` context manager. For example:

```
with pytest.raises(Exception):
    test()
```

## Logging

You can set the log level from the CLI. Use the `--log-cli-level` switch (e.g. `--log-cli-level=INFO`).
See [this Stack Overflow answer for details](https://stackoverflow.com/a/55451980/755934).

## Warnings

To disable warnings, you can pass the -W switch without any arguments.

## PYTHONPATH

`PYTHONPATH` has to be set to the top-level directory for the tests to import files from your main project. This can cause problems for automated tools. To fix this, add an `__init__.py` file in the `test` directory.

## `conftest.py`

Any fixtures declared in `conftest.py` will be automatically imported into all tests.

### fixture cleanup

All fixtures can clean up after themselves by yielding a value, then having cleanup code at the end of the fixture.

## Mock

Instead of passing a plain `mock.MagicMock` instance to mock out a class or function, you can pass an auto-spec'd instance (`mock.create_autospec`) that ensures the mocked instance is only called with valid methods and functions have the right number of arguments.

If you need to patch a method of a specific instance, you can use `mock.patch.object` instead.

## Last Failed

To rerun last failed tests, use the `--lf` switch. Can also run `--failed-first` to run failed testcases first.
