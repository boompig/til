# Data Classes

Python has data classes, which are quite handy class shorthand when all you want is to store data.
However, they have some annoying gotchas with inheritance. That's where `kw_only` comes in.

Here is something that will fail with normal data classes:

```
from dataclasses import dataclass

@dataclass
class Parent:
    a: int
    b: str


@dataclass
class Child(Parent)
    # give this a default value
    a: int = 3
    # this is a new property
    c: int

```

There is actually no way to make the example above work, with respect to reordering the parameters.
The reason is that python is trying to create constructors for the classes in the background and fails to do it.
That's where `kw_only` comes in.
You specify `@dataclass(kw_only)` for both parent and child.
Then the example will work because the constructor will be a keyword-only constructor.

