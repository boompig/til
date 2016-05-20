# Find command

Can use the find command to find only plain files

```find -f```

Can use the find command to execute a command for every file found

```
find <directory> -name <pattern> -exec <command> <args> {} \;
```

Here the `{}` refers to the filename found, and `\;` ends the list of arguments to `-exec` switch.
