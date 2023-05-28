## type predicates

Today I learned about how to use type predicates. See [this link](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#using-type-predicates).

I found that they're mostly useful for errors, since you must assign errors the type `any` or `unknown`.
So you can do this:

```
// set err.name = 'MyError'
class MyError extends Error {}

function isMyError(err: unknown) err is MyError {
    return err.name === 'MyError';
}

try {
    ...
} catch (err: unknown) {
    if (isMyError(err)) {
        // error is treated as type MyError here
    }
}
```
