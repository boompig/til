If you want to see the commits in branch A that are not yet in branch B you can run (from branch A):

```
git cherry -v B
```

The `-v` will display the commit messages (default is just to display the SHA).
Very useful when comparing trunks/environments.
