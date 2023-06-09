Eventually you get a large number of branches. How do you find the ones that haven't been merged yet?

```
git branch --no-merged master
```

Exceptionally helpful to delete some local branches that aren't useful anymore:

```
git branch --merged master
```
