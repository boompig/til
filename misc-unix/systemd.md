# Systemd Services

Writing a `systemd` service is actually very easy when starting from an existing known-good configuration.

You can use this to start your service at boot. More details [here](https://askubuntu.com/a/919059).

You can get access to the logs by running this command

```
journalctl -u service-name.service -b
```

See [this answer](https://unix.stackexchange.com/a/225407/24669) for details.
