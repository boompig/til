If you want to only stash files that have not been added to a commit you can run:

```
git stash save --keep-index
```

And to also stash those files that are untracked by git:

```
git stash save --keep-index -u
```
