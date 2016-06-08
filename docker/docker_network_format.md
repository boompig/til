Can use this command to get network information about a docker container

```
docker inspect --format '{{ NetworkSettings.Networks.<network_name>.IPAddress }}' <container name>
```
