# Logging

## logging.exception

Obviously various messages can be logged with `logging.debug` and friends.
However there is another function that's very helpful in exception handlers: [logging.exception](https://docs.python.org/3/library/logging.html#logging.exception).
This useful function will not just log the current exception, it will also log a detailed stack trace!

You can also include exception info in a given exception by setting the optional parameter `exc_info=True`
