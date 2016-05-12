Delete everything inside parens:

```c

printf("Hello world\n");

```

all ops have to be inside parens:

* `ci(` to change inner stuff
* `di(` to delete (and cut into register ")
* `vi(` to select

apparently parens are a 'block', so can also do

* `dib`, etc.

by the way can do same thing with quotes

* `di"` inside quotes to grab text inside quotes

to select including quotes/parens, use a instead of i

* `da"`
