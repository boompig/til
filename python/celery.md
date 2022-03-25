# Celery

Running background tasks using `ThreadPoolWorker` from concurrent.futures is not reliable.
It is better practice to use a task queue such as [Celery](https://github.com/celery/celery).
Celery is a system which employs message passing to coordinate background worker processes (workers).

The documentation of the Celery project is quite bad.
First of all, the main website for the project has a bad (malicious?) TLS certificate.
Second, while there are instructions for how to combine Celery with Flask, they are missing key steps.
They also fall apart as soon as you use the (recommended) pattern of an application factory.

Here are some resources I found helpful when setting up Celery:

- [Flask with Celery - basics](https://flask.palletsprojects.com/en/2.0.x/patterns/celery/)
	- Note that the command to start should point at the celery object, not just at the module
- Setting up logging is non-trivial. I found [this page](https://www.distributedpython.com/2018/11/06/celery-task-logger-format/) helpful
- [This resource](https://blog.miguelgrinberg.com/post/celery-and-the-flask-application-factory-pattern) was helpful in getting celery to work with application factory
