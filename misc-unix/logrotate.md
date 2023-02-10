# logrotate

logrotate is a utility to automatically rotate logs.

This can be extremely helpful for access/error logs on servers which can grow to enormous sizes if left unchecked.
Here is a nice sample configuration for a project called "hemingway".

```
/var/log/hemingway/access.log
/var/log/hemingway/error.log
{
    missingok
    notifempty
    rotate 30
    weekly
    compress
    delaycompress
    dateext
    dateformat -%Y-%m-%d-%s
    sharedscripts
    extension .log
    postrotate
    service nginx reload
    endscript
}
```
