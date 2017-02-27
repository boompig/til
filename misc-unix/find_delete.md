# Find and Delete

You can specify a command for `find` to execute upon finding a file. For example:

`find . -name '*.py' -exec pyflakes {} \;`

Will find all python files and run pyflakes on them.

You can also use this to delete all matching files.

`find . -name '*.pyc' -exec rm {} \;`

However this is slow because it spaws a subshell for each file found. `find` has a built-in `-delete` command. So this would look like:

`find . -name '*.pyc' -delete`
