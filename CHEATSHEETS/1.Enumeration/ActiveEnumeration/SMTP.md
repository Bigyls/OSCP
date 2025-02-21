### Linux

```shell
nmap -v --script smtp-commands,smtp-open-relay -p 25 $TARGET
```

```shell
nc -nv $TARGET 25
```

#### Hydra

```shell
hydra smtp-enum://$TARGET/vrfy -L `fzf-wordlist`
```

#### Send mail via SMTP and NetCat
```shell
nc -C $TARGET 25
HELO
MAIL FROM:$SENDER_USERNAME@local
RCPT TO:$RECEIVER_USERNAME@local
DATA
Subject: Approved in the job

http://$TARGET/malware.exe

.
QUIT
```

### Windows

```powershell
Test-NetConnection -Port 25 $TARGET
```

```powershell
dism /online /Enable-Feature /FeatureName:TelnetClient
```

