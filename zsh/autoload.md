You can export functions from dotfiles. Use the `autoload` zsh command.
Example:

```bash
function say_hello {
    if [ $# -eq 0 ]; then
        echo "usage: $0 name">&2
        return
    fi
    echo "hello $1"
}
autoload hello
```
