To profile a python file, can run:

```
python -m cProfile -s tottime <filename> <args>
```

Instead of `-s tottime` can also specify `-s cumtime`

You can also profile a test case in the same way:

```
python -m cProfile -s tottime -m pytest <testfile> -k <filter>
```
