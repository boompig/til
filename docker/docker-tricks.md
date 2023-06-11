# Docker Tricks

## incantation to map docker port to host port

`docker run -p <host_port>:<container_port> <container_name>`

## ignore build cache

To ignore the build cache, can run build with `--no-cache`! Helpful when the container is in a weird state.
