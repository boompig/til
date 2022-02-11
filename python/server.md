# Server Frameworks

## Flask

I previously used the [flask](https://flask.palletsprojects.com/en/2.0.x/) web framework (for example on BotSight, Doppelganger, PassZero, etc.).
It's a good framework, as it's lightweight and has a lot of extensions and documentation for 90% of use-cases.

To speed it up, you're supposed to put it behind a reverse-proxy like [Gunicorn](https://github.com/benoitc/gunicorn).
The idea is that Flask by default processes a single request at a time, which is obviously bad. Gunicorn will multiplex HTTP requests and call python via WSGI.

Flask can auto-generate documentation on the APIs you with Swagger/OpenAPI.
There are nice extensions that provide this out of the box. The main one I like is [Flask-RESTX](https://github.com/python-restx/flask-restx).

## FastAPI

I'm now trying [FastAPI](https://github.com/tiangolo/fastapi), which is an alternative to Flask.
Its main selling points are that it's much faster (apparently on par with Go and Node.js), and that it supports type hints for parameters via Pydantic.

The main reason for the speed increase is the use of ASGI over WSGI (asynchronous vs synchronous).
FastAPI still handles only one request at a time (albeit asynchronously) so you're supposed to put it behind a `uvicorn` reverse-proxy, which basically functions the same as Gunicorn but has ASGI support.
