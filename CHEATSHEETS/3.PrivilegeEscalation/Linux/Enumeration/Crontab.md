```shell
ls -lah /etc/cron* # Print scheduled tasks
crontab -l
```

```shell
find /etc/cron* -type f -perm -o+w -exec ls -l {} \; # Check for tasks that are run as root and are world writable
```

```shell
grep "CRON" /var/log/syslog # Check for running crontab in logs
```