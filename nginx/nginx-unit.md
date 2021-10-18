# NGINX Unit

[NGINX Unit](https://unit.nginx.org/) is a dynamic application server which can also serve as a static file server and a reverse-proxy.
Its main use is the easy configuration of dynamic languages such as Python with the performance of NGINX.

Configuration can be managed as a file just like NGINX.

## Flask

It's very easy to enable Flask. Follow [these instructions](https://unit.nginx.org/howto/flask/).

## Serving Static Files

Instead of handling requests for static files with Flask, you can handle the request for static files with NGINX.
Instructions [here](https://unit.nginx.org/configuration/#static-files).

## Enabling Access Logs

The documentation is not complete here.
You can see a working example of how to enable access logs [here](https://github.com/nginx/unit/issues/34#issuecomment-389189171).
