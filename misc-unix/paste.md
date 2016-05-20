# The paste command

Usually the command is used to merge multiple lines of files.

There is one cool use case: summing numbers from a file

```
paste -s -d+  infile | bc
```

Where `bc` is the calculator program

Basically what this does is (1) merge lines in order, and (2) replace each newline with a `+`
