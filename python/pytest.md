# Testing

Individual tests can be selected with the `-k` switch

Usually you want to specify `-x`: stop after first failed test

## Output Capture

Normally when all tests pass, there is no output.
This can be annoying when trying to collect metrics.

To disable output capture, use the `-s` switch.

## PYTHONPATH

`PYTHONPATH` has to be set to the top-level directory for the tests to import files from your main project. This can cause problems for automated tools. To fix this, add an `__init__.py` file in the `test` directory.
