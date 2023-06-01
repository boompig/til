Git 2.3 introduced 2 new commands which replace `git checkout`:

- `git switch` which is a quick way of creating and switching between branches
    - `git switch <branch>` to switch, `git switch -c <new-branch>` to create and switch
    - this is especially useful because switch is shorter than checkout to type
- `git restore <file>` to restore files. Previously with `git checkout -- <file>`
