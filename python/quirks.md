# Mypy

For some reason, this code example doesn't work:

```
from typing import TypedDict


class A:
    def foo(self) -> dict:
        return {
            "hello": "world"
        }


class MyTypedDict(TypedDict):
    hello: str
    another: str


class B(A):
    def foo(self) -> MyTypedDict:
        return {
            "hello": "world",
            "another": "key"
        }


if __name__ == "__main__":
    x = B()
    d = x.foo()
    print(d)
```

There is a bug report [here](https://github.com/python/mypy/issues/4976) but it's closed. TypedDict is not compatible with Dict, but it is compatible with Mapping.
